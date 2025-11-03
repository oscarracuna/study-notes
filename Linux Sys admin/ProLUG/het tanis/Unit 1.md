
# OS and Kernel
## Semantic naming/versioning:
- Given a version number MAJOR.MINOR.PATCH, increment the:
	- MAJOR version when you make incompatible API changes.
	- MINOR version when you add functionality in a backward compatible manner
	- PATCH version when you make backward compatible bug fixes

How to find out info about the OS/kernel
```shell
uname -a
```
```shell
cat /etc/*release
```

## Modules
We can add or remove without damaging other pieces.
Example:
```shell
$ lsmod

Module                  Size  Used by
vmnet                  73728  13
vmw_vsock_vmci_transport    49152  0
vsock                  61440  1 vmw_vsock_vmci_transport
vmw_vmci              106496  1 vmw_vsock_vmci_transport
vmmon                 163840  0
snd_seq_dummy          12288  0
snd_hrtimer            12288  1
nvidia_uvm           2060288  0
nvidia_drm            131072  14
zram                   53248  1
```

## Mount points
Map what's going on with block devices(disks) in system and the places that they exist in the file system.
```shell
$ df -h

Filesystem      Size  Used Avail Use% Mounted on
tmpfs           1.6G  2.0M  1.6G   1% /run
/dev/sdd1       106G   61G   40G  61% /
tmpfs           7.8G  109M  7.7G   2% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
tmpfs           1.6G  120K  1.6G   1% /run/user/1000
```
