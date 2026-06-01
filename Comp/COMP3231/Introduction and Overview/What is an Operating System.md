For the purposes of this course we will define and refer to operating systems based off of their lower level management of hardware rather than the higher level menus and collection of apps that is often referred to as an operating system.

## The role of the operating system
There are 2 main roles of the operating systems
### Abstractions
The operating system is to provide an **abstract machine** that coders can interface with so that they do not need to write code for every type of **hardware**.
### Resource allocation
The hardware on a system is finite and thus the operating system has to **allocate resources** to different users in a fair way such that users do **not starve**

## User Kernel Distinction
To enforce the properties of an operating system we need some mechanism from the hardware. In all modern hardware this comes in the form of a single bit, the **privileged bit**. This bit limits what we can and can't do and thus allows us to enforce some level of rules.

Operating systems are often segmented like so:
![[Pasted image 20260601162850.png]]
The software that runs in privileged mode is called the **kernel**. With the extended privilege of the operating system comes an extra level of **responsibility** as if the kernel crashes there is nothing to fall back.

Further, if an application gains code execution in the privileged mode there is no longer any restrictions.
## Structures of modern operating systems
Different operating systems are structured differently however most have a monolithic structure and are refereed to as a "spaghetti nest" where everything is tangled in with everything else.
![[Pasted image 20260601170312.png|200x200]]
