
# What is a Process?
It's an instance of one or more related tasks (threads) executing on your computer.
It is **not** the same as a program or a command.
A single command may start several processes.

![[Pasted image 20251128210736.png]]

## Processes
Processes use resources such as memory, CPU cycles and peripheral devices.
The OS (especially the kernel) is responsible for allocating a proper share of these resources.


# Process Types

Processes can be of different types according to the task being performed.

| **Process Type**          | **Description**                                                                                                                                                                                                                                                                                                                                              | **Examples**                           |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------- |
| **Interactive Processes** | Need to be started by a user, either at a command line or through a graphical interface such as an icon or a menu selection.                                                                                                                                                                                                                                 | bash, firefox, top, Slack, Libreoffice |
| **Batch Processes**       | Automatic processes which are scheduled from and then disconnected from the terminal. These tasks are queued and work on a FIFO (First-In, First-Out) basis.                                                                                                                                                                                                 | updatedb, ldconfig                     |
| **Daemons**               | Server processes that run continuously. Many are launched during system startup and then wait for a user or system request indicating that their service is required.                                                                                                                                                                                        | httpd, sshd, libvirtd, cupsd           |
| **Threads**               | Lightweight processes. These are tasks that run under the umbrella of a main process, sharing memory and other resources, but are scheduled and run by the system on an individual basis. An individual thread can end without terminating the whole process and a process can create new threads at any time. Many non-trivial programs are multi-threaded. | dconf-service, gnome-terminal-server   |
| **Kernel Threads**        | Kernel tasks that users neither start nor terminate and have little control over. These may perform actions like moving a thread from one CPU to another, or making sure input/output operations to disk are completed.                                                                                                                                      | kthreadd, migration, ksoftirqd         |

# Process Scheduling and States

The [[scheduler]] constantly shifts processes on and off the CPU, sharing time according to relative priority, how much time is needed and how much has already been granted to a task.

When a process is in a **running state**, it's either executing instructions on a CPU or is waiting to be granted a share of time. All processes in this state reside on a **run queue**. In a computer with multiple CPUs or cores, there is a run queue on each.
![[Pasted image 20251128213022.png]]

## Process Scheduling and States

Processes go into a **sleep** state when they are waiting for something to happen before they can resume. At this point, it's said the process is in a **wait queue**.

Some other less frequent states are:
- Terminating
- Zombie state (when a process' parent process has not asked about its state - not alive but still shows up)


# Process and Thread IDs

The OS keeps track of processes by assigning each a unique **process ID** ([[PID]]). Which is used to track process state, CPU usage, memory use, where resources are located in memory and other stuff.
PIDs are assigned in ascending order as they're born.
PID 1 is `init` (system initialization process).

| ID Type                  | Description                                                                                                                                                       |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Process ID (PID)         | Unique Process ID number.                                                                                                                                         |
| Parent Process ID (PPID) | Process (Parent) that started this process. If the parent dies, the PPID will refer to an adoptive parent; on modern kernels, this is kthreadd which has PPID=2.  |
| Thread ID (TID)          | Thread ID number. This is the same as the PID for single-threaded processes. For a multi-threaded process, each thread shares the same PID, but has a unique TID. |

# Terminating a Process
How do you terminate a process?

```
kill -SIGKILL <pid>
```
Or
```
kill -9 <pid>
```

**You can only kill your own processes!**
Funnily enough, the command `kill` can be used to send any kind of signal to a process, not just a termination one.
![[Pasted image 20260118164015.png]]

# User and Group IDs
The OS identifies the user who starts a process by the **Real User ID** (RUID) assigned to the user.

The user who determines the access rights for the users is identified by the **Effective UID** (EUID), which may or may not be the same as their RUID.

At the same time, there are group IDs, so there are also Real Group IDs and Effective Group IDs (RGIDs and EGIDs).


# More About Priorities
Higher priority processes get preferential access to the CPU.
The priority for a process can be set by specifying a **nice value**. *The lower the nice value, the higher the priority*.
A nice value of `-20` represents the highest priority and `+19` represents the lowest.

> You can modify the nice value of a process by using `renice +1 <pid>` where the first argument is the increase or decrease of niceness.

