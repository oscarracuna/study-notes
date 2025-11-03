

Linux system administrators spend a significant amount of their time at a command line prompt. There is a saying, "graphical user interfaces make easy tasks easier, while command line interfaces make difficult tasks possible".

The CLI provides the following advantages:
- No GUI overhead is incurred.
- Virtually any and every task can be accomplished while sitting at the CLI.
- You can implement scripts.
- You can sing into remote machines anywhere on the internet.
- While GUI tools may vary among distros, the CLI does not.

# Basic Utilities
- cat: used to type out a file or combine files.
- head: used to show the first few lines of a file.
- tail: used to show the last few lines of a file.
- man: used to view documentation.
The pipe `|` is used to have one program take the input of another.


# The Command Line

Most input lines entered at the shell prompt have three basic elements:
- Command
- Options
- Arguments
The command is the name of the program or script you're executing. It may be followed by one or more options/switches which modify what the command may do. Options usually start with one or two dashes, for example `-p or --print`.

Plenty of commands have no options or arguments.

# Sudo
`sudo` allows users to run programs using the security privileges of another user, generally root (superuser). 
Some distros come with an already set up `sudo`, you have to set it up yourself to work properly on some other distros.

# Steps for setting up and running sudo

Let's say that your distro did not come with sudo set up or installed. The preferred method of doing admin tasks is with `sudo`, but since it's not set up, we cannot use it.
Instead, we can become root by using `su` (switch user).

Now we need to create the config file to enable your account to use sudo. Typically this file is created in `/etc/sudoers.d/` and you name the file as your username.
For example: `/etc/sudoers.d/student`.
Then inside that file, you type the following:
`student ALL=(ALL) ALL`

Furthermore, some distros will complain if you do not also change the permissions on the file by doing `chmod 440 /etc/sudoers.d/student`.

# Virtual Terminals
[[Virtual Terminals]] (VT) are console sessions that use the entire display and keyboard outside of a graphical environment. They're called virtual because only one of them remains visible at all times even though we can have multiple active terminals. A VT is not the same as a command line terminal window since we can have many of those at the same time on a graphical desktop.

One virtual terminal (usually VT 1 or VT 7) is reserved for the graphical environment and the rest are displaying text logins when unused.

You can use VTs when having issues with the graphical environment.

To switch between VTs press `CTRL+ALT+F1 through F7`. Each F key corresponds to a VT. F6 for VT 6, for example. 
![[Pasted image 20251016003759.png]]
You can use `systemctl stop [name of your graphical desktop]` to stop the graphical interface. 