Bash is the most common shell (alongside a complete scripting language) used in the linux installs. Most of what is discussed here can readily be applied to alternatives like [fish]() and [zsh](), among others.
## But first, a little introduction
Whenever you do anything with your machine, it interacts with your hardware indirectly. The [[kernel]] is what has barebones control of your entire hardware, and acts as an abstraction layer for other programs to be able run in cooperation. When a command is run through bash, it reaches out to a binary stored somewhere on your system (details of which will be discussed later), and invokes it on your machine, which then interacts with the kernel. All this is to say, all your programs are but binaries too, and are therefore commands too. You can, therefore, install new commands to your install by adding more binaries that bash can invoke!
The commands listed below are binaries that are included with the linux kernel, and a brief description is added alongside.
Whenever you start a terminal session, you essentially start as the user that you are logged in as in your home directory (think of your terminal session as an agent that does the operations you need to do for you, except that every program that you use also uses this agent to interact with your machine, but that makes not a hint of difference here.). Whatever operations you perform are by default performed in your working directory, unless the binary you run changes something of the global scope.

## `ls`
`ls` is likely one of the most used commands in all of linux. The command simply *l*i*s*ts the files and directories in the current working directory. Using the `-l` flag (in the syntax `ls -l`, as using this syntax is universal for all commands, we will omit it moving forward) lists all the files and directories in the current working directory with a little more information tacked on. This command is very useful when you quickly need to get your bearings from inside of the terminal session.
Additionally, the command accepts passing in an argument in the form of a directory, in which case it lists the contents of the input directory (in the syntax `ls PATH/TO/REQUIRED/DIRECTORY`, note that this syntax is very common, and we will therefore omit to mention the space to pass inputs syntax for future binaries.)
There are some facts with regards to paths in terminals that are worth remembering --
- The path passed in as argument to this binary is absolute, ie, it starts at the root (`/`).
- `~` expands to your user's home directory
- `..` expands to the current working directory's parent
- `.` expands to the current working directory
Since these shortcuts are universal, we will also omit explaining these again moving forward.
#### Examples
`ls -l ~/Downloads` will list details for all the files in the user's home directory, along with their names
`ls /etc/` will list out all the files in `/etc/`

## `mkdir`
`mkdir` stands for *m*a*k*e *dir*ectory. It expects one argument, `target`. When invoked, it creates a new target directory at the required path if the `target` does not exist. In case it does, the process exits with an error log and does not touch the existing directory
#### Examples
`mkdir /etc/newconfigs` creates a directory called `newconfigs/` under `/etc/`

## `rmdir`
`rmdir` stands for *r*e*m*ove *dir*ectory. It expects one argument, `target`. It is used to remove empty directories. When invoked it removes the `target` directory if it is empty. If `target` has contents it will complain and not touch the `target`.
#### Examples
`rmdir /etc/newconfigs` removed the empty directory `newconfigs/` residing in `/etc/`

## `rm`
`rm` stands for *r*e*m*ove. It expects one argument, `target`. If the target is a file it removes the file. If the target is a non empty directory it will complain as such. This can be overcome by using the `-rf` flags, which will force recursion and remove the directory along with all its contents.
#### Examples
`rm ~/.config/uselessprogram/useless.conf` removes the file called `useless.conf` residing in `~/.config/uselessprogram/`
`rm -rf ~/.config/uselessprogram/` removes all the files and subdirectories residing in `/.config/uselessprogram/`, following which it removes the directory `uselessprogram/` residing in `~/.config`.

## `pwd`
`pwd` literally stands for *p*rint *w*orking *d*irectory. As the name may suggest, it simply prints to the terminal (through the stdout stream) the current working directory of the terminal session
## `cd`
`cd` stands for *c*hange *d*irectory. Continuing the tradition of descriptive command names, invoking this binary simply changes the working directory of your session to whatever you pass into it (as explained above).
#### Examples
`cd ..` will move to the parent directory of the working directory
`cd ./Downloads/` will move to the subdirectory `Downloads/` within the current working directory
## `mv`
`mv` stands for *m*o*v*e. The command expects two arguments, one for the `inputfile` and one for the `outputfile`, in the syntax `mv inputfile outputfile`. When invoked, it creates another file at the path supplied in `outputfile` with the contents of the file pointed to by `inputfile`. Additionally, it removes the `inputfile`. This makes it very useful for renaming files alongside moving them
#### Examples
`mv ~/Downloads/verygoodsong.mp3 ~/Music/bestsongever.mp3` moves the file called `verygoodsong.mp3` residing within `~/Downloads`/ to `~/Music/`, and renames it to `bestsongever.mp3`

## `cp`
`cp` stands for *c*o*p*y. The command operates largely similar to `mv`, with largely the same syntax, i.e., `cp inputfile outputfile`. It differs from `mv` only in that it does not remove the `inputfile`.
#### Examples
`cp ~/Downloads/verygoodsong.mp3 ~/Music/bestsongever.mp3` copies the file called `verygoodsong.mp3` residing within `~/Downloads`/ to `~/Music/`, and renames the freshly created copy to `bestsongever.mp3`

## `touch`
`touch` stands for... who knows what. `touch` expects one argument into it, `file`, and when invoked, it simply creates a new, empty file at the location pointed to by `file`. If the file already exists, then touch simply ignores the call and exits silently, without `touch`ing the `file`.
#### Examples
`touch ~/.config/somestupid.conf` creates a new and completely empty file at `~/.config` called `somestupid.conf`

## `echo`
`echo` stands for ... echo. It expects a single argument, which we here call `string`. When invoked, it outputs the `string` to the `stdout` bytestream.
#### Examples
`echo 'Hello World!'` outputs `Hello World!` to the terminal.
## `cat`
`cat` stands for con*cat*enate. It expects a single argument, `file`. When invoked, it fetches the contents of the file pointed to by `file` and concatenates it to the `stdout` bytestream.

## `ln`
`ln` stands for *l*i*n*k. It expects two arguments `target` and `linkname`. When used it creates a symbolic link (symlink) at `linkname`, which functions as a "highway" to another file. When any process (even if done directly by the user using something like `cat`) tries to access `linkname` it returns the `target` file/directory instead, so that that file is directly operated on, from a different location on disk.
#### Examples
`ln /etc/conf/ ~/.config/etcconfs` creates a new symlink to `/etc/conf/` at `~/.config` called `etcconfs`. When accessed, it redirects to `/etc/conf/`, our target directory
 
## `ps`
`ps` stands for *p*rocess *s*tatus. When invoked, it lists the processes that are currently running.

## `ifconfig`
`ifconfig` stands for *i*nter*f*ace *config*uration. It can accept an `interface` argument, which is used to either pull an interface `up` or `down`, among other configuration. In case `interface` is not provided it simply lists details about all network interfaces connected to the machine.
#### Examples
`ifconfig wlan0` lists out details for the interface `wlan0`

## `lsblk`
`lsblk` stands for *l*i*s*t *bl*oc*k*s. It lists all the data blocks (drives) connected to the machine, and their partitions in a tree structure.

## `lsof`
`lsof` stands for *l*i*s*t *o*pen *f*iles. When invoked, a list of currently open filestream objects is streamed to `stdout`.

## `df`
`df` stands for *d*isk *f*ree. When invoked it prints out information on usage of the various filesystems (with respect to partitions) on the machine.

## `du`
`du` stands for *d*isk *u*sage. It expects one argument, `file`. When invoked it summaries the disk usage of the `file`(s) passed into it. If no argument is give it performs this operation on every file within the system.

## `free`
`free` stands for *free* memory. When invoked it lists out the amount of total, in use, and free memory available to the machine.

## `uname`
`uname` stands for *u*ser*name*. When invoked directly it prints the name of the current kernel type. The real meat, however, lies in the use flags of the binary. A couple are listed below. It is highly recommended to check `man uname` for a more complete description.
#### Examples
`uname -a` prints all the system information of the system
`uname -s` prints the kernel name
`uname -n` prints the name of the node the system forms in a network
`uname -r` prints the kernel release version

## `uptime`
`uptime` stands for uptime. When invoked it simply outputs the time since the user logged in.

## `fdisk`
`fdisk` stands for *f*ormat *disk*. It is an incredibly powerful utility to alter the partitioning table. I.e, creating new partitions, formatting existing partitions to a new file system, and resizing partitions.

## `modprobe`
`modprobe` stands for *mod*ule *probe*. It expects one argument, `module`. When invoked, it loads the kernel `module` passsed into it as the argument into the kernel. This is especially useful when drivers for certain hardware devices (like network cards) fail to load up automatically at boot. Using this manually loads up the driver into the Kernel and makes the device operable again (assuming of course that both the driver and the hardware are functional). The kernel modules are loaded from `/lib/modules/kernelrelease/`, where `kernelrelease` is the release version of the kernel currently booted.
#### Examples
`modprobe dumbnetworkcard` loads the kernel module living at `/lib/modules/kernelrelease/` called `dumbnetworkcard`
 ``
## `chroot`
`chroot` stands for *ch*ange *root*. It expects one mandatory argument, `newroot`, and another optional argument, `command`. When invoked, it runs `command` as if the root directory were `newroot` (ie roots into a new folder). If no `command` is given, it runs `"$SHELL" -i` , in other words, it starts a new shell rooted at `newroot`. This makes it especially useful for running emergency repairs on a broken install that fails to boot from, for example, a liveboot environment by giving the user a terminal with access to a broken install (that they otherwise just would not have)
#### Examples
`chroot /mnt/brickedinstall/` starts a new shell session with the root directory as  `/mnt/brickedinstall/`
`chroot /mnt/secondarydrive/ ls usr/bin/` runs `ls /usr/bin/` at `/mnt/secondarydrive/`, but importantly, using the `ls` that lives in `/mnt/secondarydrive/usr/bin/` 

## `sudo`
`sudo` stands for *s*uper *u*ser *do*. It expects one argument, `command`. It is likely the most used command in all of linux. When invoked it runs `command` with elevated, root privileges. It is useful if running a command failed with `permission denied`.
#### Examples
`sudo touch /uselessfile` runs `touch /uselessfile` as root (which is required for messing about in the `/`)

## `chmod`
`chmod` stands for *ch*ange *mod*e. It expects two arguments, `mode` and `file`. When invoked it changes the permissions of the `file` according to `mode`.
#### Examples
`chmod +x ~/badexec` gives e*x*ecutable permissions (leaving the others that previously existed unchanged) to the file called `badexec` in `~`
`chmod -x +rw ~/Downloads/piratedgame` gives  *r*ead and *w*rite permissions to the file called `piratedgame` in `~/Dowloads/` and takes away the e*x*ecutable permissions.

## `chown`
`chown` stands for *ch*ange *own*er. It expects two arguments, `user` and `file`(s). When invoked, it makes `user` the owner of the `file` (`user` can be used with groups if done with `user:group`).

