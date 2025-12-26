

Tool used to get shells on windows machines with valid AD credentials
```
evil-winrm -i [ip] -u [username] -p ['password']
```

You can transfer files from local to winrm by CD into the dir you want your shit and then doing:
```
upload /file/to/exploit
```
No need to specify the path, it uploads to the dir you're currently located.