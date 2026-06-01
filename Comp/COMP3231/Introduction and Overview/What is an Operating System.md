For the purposes of this course we will define and refer to operating systems based off of their lower level management of hardware rather than the higher level menus and collection of apps that is often referred to as an operating system.

## The role of the operating system
There are 2 main roles of the operating systems
### Abstractions
The operating system is to provide an **abstract machine** that coders can interface with so that they do not need to write code for every type of **hardware**.
### Resource allocation
The hardware on a system is finite and thus the operating system has to **allocate resources** to different users in a fair way such that users do **not starve**

## Basic structure
![[Pasted image 20260601162850.png]]
Software that runs in privileged mode are called the kernel and can not fail because there is nothing that it can fall back to. Further, if an application gains code execution in the privileged mode there is no coming back hence 
