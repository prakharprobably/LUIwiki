This guide is aimed at complete linux beginners or those who are thinking about switching to linux.
## What is Linux, in the first place?
Linux is a family of UNIX-like operating systems based on the linux kernel which was developed by Linus Torvalds in 1991. It's open-source and has over a thousand distributions. 

## What's a Kernel?
A kernel is a software abstraction for the hardware. In short, it is what lets programs that you run use your hardware by allocating them hardware. It also manages the various processes and keeps them seperate so that they do not conflict with each other. Without a kernel, each process would have to communicate with all the other processes by itself and then allocate itself resources.

## what is a linux distro?
Distro is short for Distribution. A linux distro is a linux distribution, that's usually just a "package" that has the kernel and some supporting software, like a package manager, or if the distro is userfriendly enough, a Desktop Environment and a GUI settings utility.

## which distros are the userfriendly ones?
There are quite a few beginner-friendly distros. Some popular choices are:
1. [Linux mint](https://linuxmint.com): Linux mint comes in three flavours- XFCE, MATE & Cinnamon. You can choose whichever one you like.
2. [Pop_OS](https://system76.com/pop/): a great option if you have an NVIDIA gpu as it comes with NVIDIA drivers out of the box. Also, a solid distro if you want to do gaming.
3. [Fedora linux](https://fedoraproject.org/): Provides cutting-edge software without compromising stability. If you want the latest packages and a secure system then fedora might be the perfect distro for you.

There are many other distros, and this list is by no means exhaustive. These three have been mentioned for the sake of simplicity and brevity.
It is worth adding here that a lot of linux users "distrohop", so it matters not what you choose, you can always switch, and keep switching, until you find one that feels like home.

Don't fuss it too much:) 

If unsure, you can try these distros on a virtual machine to get a hang of what it feels like to use before committing fully.

## What's a Virtual Machine?
A Virtual Machine, commonly called a VM, is a program that emulates another kernel inside it. This kernel can then run processes, so that the processes get the native kernel environment for execution.

**In simpler terms, they're a computer running inside a computer**

VirtualBox and VMware are the most popular hypervisors for creating and managing virtual machines.

[VirtualBox setup guide](https://youtu.be/wX75Z-4MEoM?si=ktldTXmbQIFW9nlI)

[VMware setup guide](https://youtu.be/XzD8JIAOk2I?si=olpdlTaLvUag4jt-)

Cool, so you've entered the world of linux wizards. Now it's time to dive deeper and learn how to efficiently use and manage your system. 

## My machine is pretty old, will I be fine?
If you are running a computer with low resources, run a lighter desktop environment(DE), if possible, try to use a Window Manager instead of a Desktop Environment, as they are lighter on system resources. 
Almost all the distros have XFCE, LXDE, LXQT or MATE options. You can pick whichever one is available in your preferred distro.

## Whats a Display Server/Compositor
A display server is a process (you shall see that a lot of processes that run in the background are commonly referred to as servers. It is for this reason that you are reccomended to avoid thinking of a powerful computer running in the cloud at the mention of the word "server") that runs in the background and manages input and display. Earlier the display server used to be X11, however, X11 has gotten rather obsolete with time.

Wayland is a display protocol that replaced X11. Under Wayland, a program called the compositor is given the task of acting as a display server (i.e, managing events like mouse movements, window activations, keystrokes, etc.). The clients to this server are the various wndows that are to be 

## How do I learn linux?
There is no single way to learn Linux, and it largley depends on what you choose to do with your install, with many different non linear paths that can be pursued at any time, and in largley any order. However, it is reccomended that you start by learning the basic commands that will let you navigate the system.
1. [linuxjourney](https://labex.io/linuxjourney). One of the best resources for learning linux basics. After going through it, you'll know everything about linux internals like the kernel, shell and filesystem and will know how to navigate using the command line like a pro.
2. [Overthewire Bandit](https://overthewire.org/wargames/bandit/). Another great resource for getting the basics of linux down. This is an interactive game designed to teach the linux basics.

After completing these, you are well-equipped to explore the world of linux on your own.

## Where to get help?
1. General help: [r/linux4noobs](https://www.reddit.com/r/linux4noobs/): a warm community for helping new linux users.
2. Choosing a distro: [r/Distrohopping](https://www.reddit.com/r/DistroHopping/)/[r/distroreviews](https://www.reddit.com/r/distroreviews/).
3. Gaming help: [r/linux_gaming](https://www.reddit.com/r/linux_gaming/).
4. Hardware help: [r/linuxhardware](https://www.reddit.com/r/linuxhardware/).

