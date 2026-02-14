## Troubleshooting: A beginner's guide
Troubleshooting can be a difficult task, especially for beginners. However, with a systematic approach and some fundamental knowledge, you can effectively diagnose and resolve issues that may arise. Here's a step-by-step guide:

### 1. Understand the problem
The first step to troubleshooting is to gain a clear understanding of the problem you are facing. Ask questions and gather as much information as possible. Knowing the symptoms and the context in which the issue occurred can be immensely helpful.

_What exactly are you experiencing? Is there an error message? What is the general expectation of running a command or service or process? What is not working ?_

### 2. Check the logs
Based on the gathered information or the error message , you should check the logs for any info/error. The most important logs to check are the kernel log, application logs and the system logs. These logs can contain error messages, warnings, and other information that can help you to identify the cause of the problem. **/var/log/** is the main key folder to check the system wide logs of various processes. Have a good knowledge of this folder.

### 3. Utilize command-line tools
Linux provides a plethora of command-line tools and utilities that can help you diagnose issues. 
- 'top'('btop' is a more modern and cleaner alternative) for monitoring system resources.
- 'netstat' or 'ss' for network troubleshooting.
- 'ps' for process management.
- 'free' for memory related info.
- 'tail' or 'head' command to read the logs.
- 'grep' to catch / filter the required strings in the logs like error or warn etc
- 'dmesg' for kernel logs.
- 'df' or 'du' for disk related info.
- 'systemctl' for service related tasks like service start or stop.
- 'mount' and 'umount' for mounting and unmounting the disks etc.
If you do not know what any of these commands do then check out the man page for the command you want to run by simply running `man <command>` in the terminal. It provides you with a brief description of what the command does and it's usage and available options.
### 4. Leverage online resources
Explore online forums, communities, and knowledge bases. Often, you'll find that someone else has encountered a similar issue and shared their solution. Be cautious to not apply any random solution to your system without doing the due diligence or the analysis of the resultant impacts it can have on your system performance.

### 5. Learn from mistakes
In the world of Linux, mistakes are part of the learning process. When troubleshooting, it's possible to make errors or try solutions that don't work. Don't get discouraged when that happens, instead use this opportunity to learn and try out new solutions.


## Where to get help?
1. General help: [r/linux4noobs](https://www.reddit.com/r/linux4noobs/)/[r/linuxquestions](https://www.reddit.com/r/linuxquestions/).
2. Choosing a distro: [r/Distrohopping](https://www.reddit.com/r/DistroHopping/)/[r/distroreviews](https://www.reddit.com/r/distroreviews/).
3. Gaming help: [r/linux_gaming](https://www.reddit.com/r/linux_gaming/).
4. Hardware help: [r/linuxhardware](https://www.reddit.com/r/linuxhardware/).

