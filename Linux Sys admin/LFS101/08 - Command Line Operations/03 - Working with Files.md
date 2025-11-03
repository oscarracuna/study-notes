

Commands to work with files.
Skipping this one as it's very self explanatory.

| Command  | Usage                                                                                                                                                                                          |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **cat**  | Used for viewing files that are not very long; it does not provide any scroll-back.                                                                                                            |
| **tac**  | Used to look at a file backwards, starting with the last line.                                                                                                                                 |
| **less** | Used to view larger files because it is a paging program. It pauses at each screen full of text, provides scroll-back capabilities, and lets you search and navigate within the file.          |
| **tail** | Used to print the last 10 lines of a file by default. You can change the number of lines by doing **-n 15** or just **-15** if you wanted to look at the last 15 lines instead of the default. |
| **head** | The opposite of **tail**; by default, it prints the first 10 lines of a file.                                                                                                                  |

# touch
Used to set or update the access, change and modify times of files. (also used to create new files).
With `touch -t` you can set the date and timestamp.
![[Pasted image 20251022201648.png]]

# mkdir and rmdir 
`mkdir` is used to make a directory
`rmdir` is used to delete an **empty** directory.

# Moving, Renaming or Removing a File

|Command|Usage|
|---|---|
|**mv**|Rename a file|
|**rm**|Remove a file|
|**rm -f**|Forcefully remove a file|
|**rm -i**|Interactively remove a file|

# Modifying the Command Line Prompt
The `PS1` variable is the character string that is displayed as the prompt on the CLI.
By convention, most systems are set up so that the root user has a pound sign `#` as their prompt.