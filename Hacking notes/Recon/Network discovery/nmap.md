
Daily driver:
```shell
sudo nmap -p- --open -sS --min-rate 5000 -vvv -n -Pn <ip> -oG puertos

sudo nmap -p[ports] -sC -sV [ip] -oN openPuertos
```

http enum
```bash
nmap --script http-enum -p80 -oN nmap-fuzzing <ip>
```
