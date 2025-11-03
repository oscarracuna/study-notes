
# Linux Filesystems
Different types of filesystems supported by Linux:
- Conventional disk filesystems: `ext3, ext4, XFS, Btrfs, JFS, NTFS, vfat, exfat`, etc.
- Flash storage filesystems: `ubifs, jffs2, yaffs`, etc.
- Database filesystems.
- Special purpose filesystems: `procfs, sysfs, tmpfs, squashfs, debufgs, fuse`, etc.

# Partitions and Filesystems
A **partition** is a **dedicated subsection of physical storage media.** Historically this meant a physically contiguous portion of a hard disk; today's storage devices can be more complicated.

A **filesystem** is just a **method of storing and accessing files**.
![[Pasted image 20250831223124.png]]

# The Filesystem Hierarchy Standard
Linux systems store their important files according to a standard layout called the **[[Filesystem Hierarchy Standard]]** ([[FHS]]), which has long been maintained by the Linux Foundation. 

Linux uses the `/` character to separate paths and does not use letters for drives. Multiple drives and/or partitions are mounted as directories in the single filesystem. Removable media like USBs and CDs will show up as mounted at `/run/media/yourusername/disklabel` or under `/media` for older distros.
![[Pasted image 20250831224309.png]]

All Linux filesystem names are **case-sensitive**, so `/boot`, `/Boot` and `/BOOT` represent three different directories.