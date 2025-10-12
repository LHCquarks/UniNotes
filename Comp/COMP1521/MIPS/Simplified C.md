When we translate C code into Assembly we first translate C into simplified C to make it an easier transition.

Below are key principles:
## Single operations
Instead of writing lines like
```C
int a = 1;
int b = 2;
int c = 3;
int out = (a + b) * c;
```
we must instead write
```C
int a = 1;
int b = 2;
int c = 3;
int temp = a + b;
int out = temp * c;
```

## Branching
Instead of writing statements like
```C
if (a == b) {
	doSomething();
} else {
	doSomethingElse();
}
```
we write
```C
if (a == b) goto doSomething;
goto doSomethingElse;

doSomething:
	// Doing something
	goto boundsEnd;

doSomethingElse:
	// Doing something else
	goto boundsEnd;

boundsEnd:
	// Rest of program
```

## Splitting condition checking
Instead of writing code like
```C
if (a || b) {
	// Do someting
}
```
we can write
```C
if (a) goto doSomething;
if (b) goto doSomething;
goto endIf;

doSomething:
	// Do something
	goto endIf;
	
endIf:
	// Rest of program
```

## Demorgan
Instead of writing statements like `a && b` we can use Demorgan to write it equivalently as `!(!a || !b)`
Hence we write
```C
if (a && b) {
	// Do something
}
```
as
```C
if (!(!a || !b)) {
	// Do something
}
```
which turns into
```C
if (!a || !b) goto continueProgram;
goto doSomething;

doSomething:
	// Do something
	goto continueProgram;

continueProgram:
	// Rest of program
```
and this finally becomes
```C
if (!a) goto continueProgram;
if (!b) goto continueProgram;
goto doSomething;

doSomething:
	// Do something
	goto continueProgram;

continueProgram:
	// Rest of program
```
## While loops
### General structure
We use the code blocks:
- loop_init
- loop_condition
- loop_body
- loop_step
- loop_end
From here the general structure looks like
```C
goto loop_init;

loop_init:
	// initialize variables
	int i = 0;
	goto loop_condition;

loop_condition:
	// check condition
	if (i == 10) goto loop_end;
	goto loop_body

loop_body:
	// Do body things
	goto loop_step;

loop_step:
	i++;
	goto loop_condition;

loop_end:
	// Do the rest of the program
```

## For loops
To do this we just convert to a while loop like
```C
for (int i = 0; i < 10; i++) {
}
```
to 
```C
int i = 0;
while (i < 10) {
	i++;
}
```

## Break and continues
### Breaks
To translate a break we can just goto the loop end like so
```C
while (a == b)  {
// Some body
if (c) break;
// Something else
}
```
turns into
```C
while (a == b)  {
// Some body
if (c) goto loop_end;
// Something else
}
```
### Continue
A similar thing happens with continue except we goto the loop step function instead.