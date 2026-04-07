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
## `pwd`
`pwd` literally stands for *p*rint *w*orking *d*irectory. As the name may suggest, it simply prints to the terminal (through the stdout stream) the current working directory of the terminal session
## `cd`
`cd` stands for *c*hange *d*irectory. Continuing the tradition of descriptive command names, invoking this binary simply changes the working directory of your session to whatever you pass into it (as explained above).
## `mv`
`mv` stands for *m*o*v*e. The command expects two arguments, one for the `inputfile` and one for the `outputfile`, in the syntax `mv inputfile outputfile`. When invoked, it creates another file at the path supplied in `outputfile` with the contents of the file pointed to by `inputfile`. Additionally, it removes the `inputfile`. This makes it very useful for renaming files alongside moving them
## `cp`
`cp` stands for *c*o*p*y. The command operates largely similar to `mv`, with largely the same syntax, i.e., `cp inputfile outputfile`. It differs from `mv` only in that it does not remove the `inputfile`.

## `touch`
`touch` stands for... who knows what. `touch` expects one argument into it, `file`, and when invoked, it simply creates a new, empty file at the location pointed to by `file`. If the file already exists, then touch simply ignores the call and exits silently, without `touch`ing the `file` (ba-dum-tss).

## `echo`
`echo` stands for ... echo. It expects a single argument, which we here call `string`. When invoked, it outputs the `string` to the `stdout` bytestream.
## `cat`
`cat` stands for con*cat*enate. It expects a single argument, `file`. When invoked, it fetches the contents of the file pointed to by `file` and concatenates it to the `stdout` bytestream.
## `ps`
`ps` stands for *p*rocess *s*tatus. When invoked, it lists the processes that are currently running.

## `ifconfig`
`ifconfig` stands for *i*nter*f*ace *config*uration. It can accept an `interface` argument, which is used to either pull an interface `up` or `down`, among other configuration. In case `interface` is not provided it simply lists details about all network interfaces connected to the machine.

## `lsblk`
`lsblk` stands for *l*i*s*t *bl*oc*k*s. It lists all the data blocks (drives) connected to the machine, and their partitions in a tree structure.

## `lsof`
`lsof` stands for *l*i*s*t *o*pen *f*iles. When invoked, a list of currently open filestream objects is streamed to `stdout`.
