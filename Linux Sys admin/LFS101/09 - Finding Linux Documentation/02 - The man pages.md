
# The man pages
man pages are the most often-used source of Linux documentation. They are present on all Linux distros.

```
man [command in particular you would like to look up]
```

- `man -f` generates the same result as `whatis`
- `man -k` generates the same result as `apropos`

The default order is specified in `/etc/man_db.conf`.
![[Pasted image 20251111214022.png]]

# Manual Chapters

The man pages are divided into chapters numbered 1 through 9. Some append letters.
For example, many pages describing part of the X Window API are in chapter **3X**.
You can use the number to display the page from a particular chapter.

The `-a` parameter will display all pages with the given name in all chapters.
![[Pasted image 20251111214421.png]]

