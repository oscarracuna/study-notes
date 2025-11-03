
```
nxc smb [ip] -u 'a' -p '' --shares
```

Use this to enumerate users:
```
nxc smb [ip] -u guest -p '' --rid-brute
```

if you already have a password use this:
```
nxc smb [ip] -u user.txt -p '[password]' --continue-on-success
```
