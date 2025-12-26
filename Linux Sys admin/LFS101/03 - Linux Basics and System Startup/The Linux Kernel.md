
The boot loader loads both the kernel and an initial RAM-based file system ([[initramfs]]) into memory, so it can be used directly by the kernel.

When the kernel is loaded in RAM, it immediately initializes and configures the computer's memory and also configures all the hardware attached to the system. This includes all processors, I/O subsystems, storage devices, etc. The kernel also loads some necessary user space applications.
![[Pasted image 20250814195535.png]]

# /sbin/init and Services
Once the kernel has set up all its hardware and mounted the root filesystem, the kernel runs **[[/sbin/init]]**. This then becomes the initial process, which then starts other processes to get the system running. **Most other processes on the system trace their origin ultimately to `init`**; exceptions include the kernel processes. These are started by the kernel directly and their job is to manage internal operating system details.

Besides starting the system, `init` is responsible for keeping the system running and for shutting it down cleanly. One of its responsibilities is to act when necessary as a manager for all non-kernel processes; it cleans up after them upon completion, and restart user login services as needed when users log in and out, and does the same for other background system services.

`SysVinit` was the predecessor of `init` back in the 1980's and the V variety of UNIX. It had the system pass through a sequence of **runlevels** containing collections of scripts that start and stop services.
![[Pasted image 20250831215732.png]]

# Startup Alternatives
`SysVinit` viewed things as a serial process, divided into a series of sequential stages. Each stage required completion before the next could proceed. Thus, startup did not easily take advantage **parallel processing**.

Starting up and rebooting were seen as relatively rare events back then, which is no longer true today.

Two main alternatives developed were:

**[[Upstart]]**
- Developed by Ubuntu and first included in 2006.
- Adopted in Fedora 9 (2008) and RHEL 6.
**[[systemd]]**
- Adopted by Fedora in 2011.
- Adopted by RHEL 7 and SUSE.
- Replaced Upstart in Ubuntu 16.04.

# systemd Features
Systems with systemd start up faster than those with earlier init methods. This is largely because it replaces a serialized set of steps with aggressive parallelization techniques, which permits multiple services to be initiated simultaneously.

Shell scripts were replaced with simpler configuration files, which enumerate what has to be done before a service is started, how to execute service startup and what conditions the service should indicate have been accomplished when startup is finished.
**Now, `/sbin/init` just points to `/lib/systemd/systemd`**, so systemd takes over the init process.

The command `systemctl` is part of systemd.
Some examples:

```shell
sudo systemctl start|stop|restart

sudo systemctl enable|disable

sudo systemctl status
```
