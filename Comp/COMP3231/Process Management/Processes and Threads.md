## The problem
Almost all OS's want to run more tasks than there are cores on a cpu which means that we need a way to allocate time for each task to run. This allocation needs to be fair so that all tasks feel responsive.
## What is a process
A process is a term to describe each task and their memory.
Processes **own resources** and execute logic on one or many **threads**.
## What is a thread
Threads are units of code execution. Unlike a process it does not have it's own memory and must **share** it with other threads in the perant process.
## The Dispatcher
The **Dispatcher** is the component of an operating system that hands the management, interleaving and execution of processes.
### Seizing control
The dispatcher takes back control of the cpu when one of the following happens:
- Process is blocked (eg is waiting for IO)
- Process times out
- Process yields control (done through the yield sys call)
![[Pasted image 20260602073022.png]]
Time outs are often achieved through interrupts that occur after aprox 1ms.
### How Items are scheduled
The dispatcher generally works through a whole bunch of queues as shown below.
![[Pasted image 20260602073311.png]]
## The Process Control Block (PCB)
The PCB is a table (may or may not be a table in memory) that contains information about the current process. 