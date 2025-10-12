Functions take in values and can return values.

In MIPS we do not need to declare what our functions return nor the parameters they take in. Instead we are in charge of making all the local variables and even returning control to the original process

Functions are just labels in MIPS.

To do proper function returns we need to:
- set the $ra register with our return value
- jump to the function label
- return to our return address

The only problem is if we just follow these steps we will loose our original return address! This is called **clobbering**.

To fix this we need to create our own **Stack frame**.
## Stack frames
We can call the instructions `push R1` and `pop R2` to:
- push the value in `R1` onto the stack
- store and pop the value at the end of the stack into `R2`

When running a function we need to store the `$ra` and all `$s` registers.

Setting up a function occurs in its *prologue* and the tare down is called the *epilogue*

For debugging purposes we can use the frame pointer `$fp` to store the start of the stack frame of a function. MIPSY adds the commands `begin` and `end` to make this easier.
## Examples
### Very basic
Bellow is a function that does not return anything and does not take in any args

```MIPS
main:
	# Do things
	
	jal f # Load the next line into the $ra register and jump to f
	
	# Do other things
	li $v0, 0
	jr $ra

f:
	begin
	push $ra
	# Do things
	pop $ra
	end
	jr $ra
```

### Uses `$s` registers
Bellow is a function that takes in values and uses `$s0`
```MIPS
main:
	# Do things
	
	jal f
	
	# Do more things
	
	li $v0, 0
	jr $ra

f_prolgue:
	begin
	push $ra
	push $s0
	
f_body:
	li $s0, 1
	# Do other things

f_epilogue:
	pop $s0
	pop $ra
	end
	jr $ra
```
### Arguments
To set the arguments for a function we set the `$a` registers. This is then read in the function:
```MIPS
main:
	# Do things
	
	li $a0, 1 # load argument into $a0
	jal f
	
	# Do more things
	
	li $v0, 0
	jr $ra

f_prolgue:
	begin
	push $ra
	push $s0
	
f_body:
	move $s0, $a0 # $s0 = $a0
	# Do other things

f_epilogue:
	pop $s0
	pop $ra
	end
	jr $ra
```
### Return values
To return values just set the data in the `$v` registers.