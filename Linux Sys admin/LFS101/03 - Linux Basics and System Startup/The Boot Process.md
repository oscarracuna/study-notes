
The Linux boot process is the procedure for initializing the system. Consists of everything that happens from when the computer power is first switch on until the user interface is fully operational.

![[Pasted image 20250720193543.png]]

# BIOS - The first step
Starting an x86-based Linux system involves a number of steps. When the computer is powered on, the [[BIOS]] (**Basic Input/Output System**) initializes the hardware, including the screen and the keyboard and tests the main memory. This process is also called **POST (Power On Self Test)**.

The BIOS software is stored on a read-only memory ([[ROM]]) chip on the motherboard. After this, the remainder of the boot process is controlled by the operating system.
![[Pasted image 20250720193905.png]]

# Master Boot Record [[MBR]], [[EFI]] Partition and [[Boot Loader]]
Once the POST is completed, system control passes from the BIOS to the boot loader. The boot loader is usually stored on one of the system's storage devices such as a hard disk or SSD drive, either in the boot sector or the EFI partition. Up to this stage, the machine does not access any mass storage media. Then, information on the date, time, and the most important peripherals are loaded from the [[CMOS]] values.

A number of boot loaders exist for Linux; the most common ones are [[GRUB]] (Grand Unified Boot Loader), [[ISOLINUX]], and [[DAS U-boot]]. Most Linux boot loaders can present a user interface for choosing alternative options for booting Linux and even other operating systems that might be installed. When booting Linux, **the boot loader is responsible for loading the [[kernel]] image and the initial RAM disk or [[filesystem]]** into memory.
![[Pasted image 20250720194424.png]]

# Boot Loader in Action
Has two distinct stages:
1. **For systems using the BIOS/MBR method**, the boot loader resides at the first sector of the hard disk, also known as the **MBR**. The size of the MBR is just 512 bytes. In this stage, the boot loader examines the partition table and finds a bootable partition. Once it finds a bootable partition, then searches for the second stage boot loader, for example GRUB, and loads it into RAM.
2. **For systems using the EFI/UEFI method**, UEFI firmware reads its Boot Manager  data to determine which UEFI application is to be launched from where. The firmware then launches the UEFI application, for example, GRUB, as defined in the boot entry in the firmware's boot manager. This procedure is more complicated but more versatile than the older MBR methods.
   
   The second stage boot loader resides under `/boot`. A splash screen is displayed, which allows us to choose which OS and/or kernel to boot.Then, the boot loader loads the kernel of the OS into RAM and passes control to it. Kernels are almost always compressed, so the first job they have is to uncompress themselves. After this, it will check and analyze the system hardware and initialize any hardware device drivers built into the kernel.


# The Initial RAM Disk

The `initramfs` filesystem image contains programs and binary files that perform all actions needed to mount the proper root filesystem, including providing the kernel functionality required for the specific filesystem that will be used, and loading the device drivers for mass storage controllers, by taking advantage of the `udev` system (for user device), which is responsible for figuring out which device are present, locating the device drivers they need to operate properly, and loading them. After the root filesystem has been found, it is checked for errors and mounted.

The `mount` program instructs the operating system that a filesystem is ready for use and associates it with a particular point in the overall hierarchy of the filesystem (the mount point). If this is successful, the `initramfs` is cleared from RAM, and the init program on the root filesystem (/sbin/init) is  executed.

`init` handles the mounting and pivoting over to the final real root filesystem. If special hardware drivers are needed before the mass storage can be accessed, they must be in the initramfs image.
![[Pasted image 20250814194550.png]]


# Text-Mode Login
Near the end of the boot process, init starts a number of text-mode login prompts. These enable you to type your username, followed by your password, and to eventually get a command shell. However, if you are running a system with a graphical login interface, you will not see these at first.
**Alt + an FN (depends on the distro) gets you a command shell.**

Usually, the default command shell is bash (GNU Bourne Again Shell), but there are a number of other advanced command shells available. The shell prints a text prompt, indicating it is ready to accept commands; after the user types the command and presses enter, the command is executed and another prompt is displayed after the command is done.
![[Pasted image 20250814195354.png]]



