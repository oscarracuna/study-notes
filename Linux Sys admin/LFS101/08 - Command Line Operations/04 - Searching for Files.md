
When commands are executed, by default there are three standard file streams or descriptors always open for use:
- standard input (standard in or [[stdin]]).
- standard output (standard out or [[stdout]]).
- standard error or [[stderr]].

| Name            | Symbolic Name | Value | Example  |
| --------------- | ------------- | ----- | -------- |
| standard input  | **stdin**     | 0     | keyboard |
| standard output | **stdout**    | 1     | terminal |
| standard error  | **stderr**    | 2     | log file |

Usually, **stdin** is your **keyboard**, and **stdout** and **stderr** are printed on your terminal. **stderr** is often redirected to an error logging file, while **stdin** is supplied by directing input to come from a file or form the output of a previous command through a pipe. **stdout** is also often redirected into a file. Since **stderr** is where error messages and warnings are written, usually nothing will go there.

Internally, all open files are represented by **descriptors**. 0, 1 and 2 for stdin, stdout and stderr. If other files are opened in addition to these three, they will start at file descriptor 3 and increase from there. 

# I/O Redirection

Through the command shell, we can redirect the three standard file streams so that we can get input from either a file or another command, instead of from our keyboard and we can write output and errors to files or use them to provide input for subsequent commands.

Let's say that we have a program called `do_something` that reads from `stdin` and writes to a  `stdout` and `stderr`

```bash
$ do_something < input-file

If you want to send the output to a file, use the greater-than sign (>) as in:  
  
$ do_something > output-file

In fact, you can do both at the same time as in:

$ do_something < input-file > output-file
```

# Pipes
The UNIX/Linux philosophy is to have many simple and short programs or commands cooperate together to produce quite complex results, rather than have one complex program with many possible options and modes of operation.

So, you can pipe the output of one command or program into another as its input with pipes `|`.

```bash
$ command1 | command2 | command3
```

![[Pasted image 20251024003006.png]]

# Searching for Files
Being able to quickly find the files you are looking for will save you time and enhance productivity. 

The main tools for doing this are `locate` and `find` utilities. You can also use wildcards `*` to find any file that matches a given generalized request.

```
$ locate zip | grep bin
```
![[Pasted image 20251024003228.png]]

# Wildcards and Matching Filenames
|Wildcard|Result|
|---|---|
|**?**|Matches any single character|
|*****|Matches any string of characters|
|**[set]**|Matches any character in the set of characters, for example **[adf]** will match any occurrence of **a**, **d**, or **f**|
|**[!set]**|Matches any character not in the set of characters|

# The find Program
`find` is an extremely useful and often-used utility program in the daily life of a Linux system administrator.
It recurses down thee filesystem tree from any particular directory or set of directories and locates files that match specified conditions.
![[Pasted image 20251024004359.png]]
# Using find
When no arguments are given, `find` lists all files in the current directory and all of its subdirectories.
![[Pasted image 20251024004633.png]]

# Using Advanced find Options
The `-exec` command allows you to find files that match certain criteria.

For example, to find and remove all files that end with `.swp`, you can run
```
$ find -name "*.swp" -exec rm {} ';'
```

Or you can run `-ok`, which behaves like `-exec`, but it prompts for permission before executing the command.
![[Pasted image 20251024004945.png]]

# Finding Files Based on Time and Size

To find files based on time:
```
$ find / -ctime 3
```
Here, `-ctime` is when the inode metadata (file ownership, permissions, etc.) last changed; often this is when the file was created, but not always.

You can also search for accessed/last read with `-atime` or modified/last written times with `-mtime`.

To find files based on size:
```
$ find / -size 0
```
Thee default is 512-byte blocks, but you can also specify bytes (c), kilobytes (k), megabytes (M) and gigabytes (G).

Example of finding files greater than 10 Mb and then running a command on those files:
```
$ find / -size +10M -exec command {} ';'
```
![[Pasted image 20251024005434.png]]
