Usual command:

```
hydra -l username -P /usr/share/wordlists/rockyou.txt ftp

```
Use -l when you know the username
Use -L to use dictionary to find username

For usernames:
```
hydra -L [username list] -p test [url] http-post-form "/[url]:log=^USER^&pwd=^PWD:[invalid error message]" -t 30
```

Once we acquired username:
```
hydra -l [username] -P [pswd dictionary] [ip] http-post-form "/[url]:log=^USER^&pwd=^PWD:[invalid error message]" -t 30
```

[[Brute force]]
