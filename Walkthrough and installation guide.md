This guide is aimed at complete linux beginners or those who are thinking about switching to linux.
## What is Linux, in the first place?
Linux is a family of UNIX-like operating systems based on the linux kernel which was developed by Linus Torvalds in 1991. It's open-source and has over a thousand distributions. 

## What's a Kernel?
A kernel is a software abstraction for the hardware. In short, it is what lets programs that you run use your hardware by allocating them hardware. It also manages the various processes and keeps them separate so that they do not conflict with each other. Without a kernel, each process would have to communicate with all the other processes by itself and then allocate itself resources.

## what is a linux distro?
Distro is short for Distribution. A linux distro is a linux distribution, that's usually just a "package" that has the kernel and some supporting software, like a package manager, or if the distro is user friendly enough, a Desktop Environment and a GUI settings utility.

## which distros are the user friendly ones?
There are quite a few beginner-friendly distros. Some popular choices are:
1. [Linux mint](https://linuxmint.com): Linux mint comes in three flavours: XFCE, MATE & Cinnamon. You can choose whichever one you like.
2. [Pop_OS](https://system76.com/pop/): a great option if you have an NVIDIA gpu as it comes with NVIDIA drivers out of the box. Also, a solid distro if you want to do gaming.
3. [Fedora linux](https://fedoraproject.org/): Provides cutting-edge software without compromising stability. If you want the latest packages and a secure system then fedora might be the perfect distro for you.

There are many other distros, and this list is by no means exhaustive. These three have been mentioned for the sake of simplicity.
It is worth adding here that a lot of linux users "distrohop", so it matters not what you choose, you can always switch, and keep switching, until you find one that feels like home.

Don't fuss it too much:) 

If unsure, you can try these distros on a virtual machine to get a hang of what it feels like to use before committing fully.

## What's a Virtual Machine?
A Virtual Machine, commonly called a VM, is a program that emulates another kernel inside it. This kernel can then run processes, so that the processes get the native kernel environment for execution.

**In simpler terms, they're a computer running inside a computer**

VirtualBox and VMware are the most popular hypervisors for creating and managing virtual machines.

[VirtualBox setup guide](https://youtu.be/wX75Z-4MEoM?si=ktldTXmbQIFW9nlI)

[VMware setup guide](https://youtu.be/XzD8JIAOk2I?si=olpdlTaLvUag4jt-)

## My machine is pretty old, will I be fine?
If you are running a computer with low resources, run a lighter desktop environment(DE), if possible, try to use a Window Manager instead of a Desktop Environment, as they are lighter on system resources. 
Almost all the distros have XFCE, LXDE, LXQT or MATE options. You can pick whichever one is available in your preferred distro.

## Whats a Display Server/Compositor
A display server is a process (you shall see that a lot of processes that run in the background are commonly referred to as servers. It is for this reason that you are reccomended to avoid thinking of a powerful computer running in the cloud at the mention of the word "server") that runs in the background and manages input and display. Earlier the display server used to be X11, however, X11 has gotten rather obsolete with time.

Wayland is a display protocol that replaced X11. Under Wayland, a program called the compositor is given the task of acting as a display server (i.e, managing events like mouse movements, window activation, keystrokes, etc.). The clients to this server are the various windows that are to be 

