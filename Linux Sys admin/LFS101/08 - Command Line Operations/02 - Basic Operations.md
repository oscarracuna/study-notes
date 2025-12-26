


![[Pasted image 20251016004646.png]]

# Logging In and Out

Skipping this whole section ZzZzZZzZz


# Rebooting and Shutting Down
The preferred method to shutdown or reboot a system is with `shutdown`.
It sends a warning message and prevents users from logging in. **The init process will then control shutting down or rebooting the system.** Not shutting down correctly can cause damage to the system or data loss.

The `halt` and `poweroff` commands issue `shutdown -h` to halt the system. `reboot` issues `shutdown -r`. Both require sudo.

When administering a multi-user system, you have the option of notifying all users prior to shutdown.

`sudo shutdown -h 10:00 "Shutting down for shceduled maintenance."`

# Locating Applications
In general, executable programs and scripts should live in `/bin`, `/usr/bin`, `/sbin`, `/usr/sbin` or under `/opt`.
Also `/usr/local/bin` and `/usr/local/sbin` or inside the user's home directory.

To locate a program you can use `which` or `whereis`
If `which` does not find the program, `whereis` is a good alternative because it looks for packages in a broader range of system directories and also finds man files.

# Accessing Directories

|Command|Result|
|---|---|
|**pwd**|Displays the present working directory|
|**cd ~** or **cd**|Change to your home directory; shortcut name is **~** (tilde)|
|**cd ..**|Change to parent directory (..)|
|**cd -**|Change to previous working directory; **-** (minus)|

# Understanding Absolute and Relative Paths

- **Absolute pathname**: It begins with the root directory and follows the tree branch by branch until it reaches the desired directory or file. It always starts with `/`.
- **Relative pathname**: It starts from the present working directory. Never starts with `/`.
`.` present directory.
`..` parent directory.
`~` your home directory.

- Absolute pathname:
  `cd /usr/bin`
- Relative pathname:
  `cd ../../usr/bin`
![[Pasted image 20251017203328.png]]

# Exploring the Filesystem
The `tree` command is a good way to get a bird's eye view of the filesystem tree.
With `tree -d` you can view only directories and not files.

| Command   | Usage                                                                                    |
| --------- | ---------------------------------------------------------------------------------------- |
| **cd /**  | Changes your current directory to the root (/) directory (or path you supply)            |
| **ls**    | List the contents of the present working directory                                       |
| **ls -a** | List all files, including hidden files and directories (those whose name start with `.`) |
| **tree**  | Displays a tree view of the filesystem                                                   |

# Hard links
The `ln` utility is used to create hard links and with the `-s` option, soft links.
A.K.A symbolic links or symlinks.

Hard links are very useful and they save space, but you have to be careful with their use. If you remove either file, the *inode* object will remain, which may cause issues if unaccounted for.

If you were to edit one of the files, the outcome depends on the editor.
For example, `vi` and `gedit` will retain the link by default, but it's possible that modifying one of the names may break the link and result in the creation of two objects.

# Soft links
Symbolic links take no extra space on the filesystem. They can easily be modified to point to different places. Can be used to create shortcuts, for example.

Unlike hard links, soft links can point to objects even on different filesystems, partitions, and/or disks and other media which may or may not be currently available. In which case you obtain a *dangling link*.