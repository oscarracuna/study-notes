
```
ffuf -c -u http://10.10.11.47/FUZZ -w ~/Tools/SecLists/Discovery/Web-Content/directory-list-2.3-medium.txt -fc 301
```


```shell
ffuf -w /usr/share/wordlists/seclists/Discovery/DNS/bitquark-subdomainstop100000.txt:FUZZ -u [http://IP] -H 'Host: FUZZ.hostname' -fw 4 - t 100
```

```shell
ffuf -w /home/rhaenesis/Tools/SecLists/Discovery/DNS/subdomains-top1million-110000.txt -u http://FUZZ.linkvortex.htb -H 'Host: FUZZ.hostname' -fw 4 -mc 200 -fs 301
```

This shit requires seclists
You can install it by doing 
```shell
sudo apt install seclists
```

