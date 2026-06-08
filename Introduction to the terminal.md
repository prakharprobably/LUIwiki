The terminal is largely what you will be using to interact with your install. While this may feel intimidating at first, learning to use the terminal carries significant advantages for interacting with your install compared to a GUI, including lower resource usage and higher performance, along side increased robustness when things go sideways (as a terminal requires significantly less services to be operational, compared to a full fledged GUI).
Here, we will study briefly this way of interacting with the machine.
## What is a terminal?
A terminal, as the name suggests, is the point where processing terminates. Much like a wire terminal, inputs are taken from the terminal and outputs are delivered to the terminal.
Terminals get their name from the olden days of computing when computers used to be massive and room sized, and they would have a small console for interaction (usually via punchcards). This console was called the terminal as the processing pipelines for the cards would terminate here on both ends.
Later, when electronics and digital computing became more commonplace, this name stuck around. Now, interactions with (still massive) mainframes was done with a CRT screen (for displaying outputs) and a keyboard (for taking in inputs). The name terminal was still used for this arrangement. 
In broader contexts, now a days, terminal represents the human interface components of computing, usually via text based interactions.
## What is a terminal emulator?
As the name suggests, a terminal emulator attempts to emulate the terminals of eras gone by. Terminal emulators attempt to recreate the experience of interacting with terminals. Unlike the hardware terminals, they do not have a hardware keyboard attached, and will therefore read inputs from the external keyboard (handled by the kernel), nor do they have a screen attached, and will therefore use the monitor provided to it by the kernel.
Terminal emulators are software components to interact with the command line as hardware terminals (such as the Commodore 64) are rather rare in the modern day.

## How does the terminal work?
The terminal of the old days worked by directly handling keyboard inputs to form them into a command. It would then direct what command you built up from the combination of the keypresses into a bytestream when `Return` would be depressed.
This bytestream would then be read by the shell (for example, BASH) to parse which binaries to execute and what input to give to them while calling them.
During execution, the binaries may or may not return an output. This output is then placed by the shell into another bytestream, which is read by the terminal and parsed to form text onto the screen.
The terminal emulators of today perform a similar action, taking in the keyboard inputs offered by the kernel, parsing them into a command, and then directing that command via a bytestream to the shell, alongside reading the output (& error) bytestreams and rendering them into a window (as offered by the display server) to be rendered onto the screen.

## What are bytestreams?
A bytestream, as the name might suggest, is a stream of bytes. Bytes are, in leyman's terms, collections of bits, or rather conveniently, a unit of data. Bytestreams, then, are simply continuous pathways for the flow of data from one entity to another.
There are a couple of standard bytestreams that are of particular interest to us, and we will discuss them below --
### Stdin
`stdin` stands for *st*an*d*ard *in*put. The name is rather descriptive, as the `stdin` bytestream is the standard way for binaries to accept inputs (this is, conveniently, valid across all the major Operating Systems, including BSD and its derivatives). The `stdin` bytestream carries initial inputs and parameters to the binaries from the process calling the binary.
### Stdout
`stdout` stands for *st*an*d*ard *out*put. Continuing on the streak of descriptive nomenclature, the `stdout` bytestream is the standard way for binaries to excommunicate with the process that called them. This, yet again, is valid across all the major Operating Systems. The `stdout` bytestream carries outputs (and logs and return codes) from the binary to the process that called them. This is usually what terminals will print out as outputs and logs
### Stderr
`stderr` stands for *st*an*d*ard *err*or. This bytestream is used to carry error logs and warnings from the executed binary to the process calling the binary. Some terminals may suppress this bytestream depending on how it is invoked.

