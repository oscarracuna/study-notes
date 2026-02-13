
## Domains
```shell
sudo gobuster dir -u [http://ip] -w /home/rhaenesis/SecLists/Discovery/Web-Content/directory-list-2.3-medium.txt -t 200 -o doms.txt
```

## Subdomains
```shell
sudo gobuster dns -d test.htb -w /home/rhaenesis/SecLists/Discovery/DNS/subdomains-top1million-5000.txt -o gobuster_subdomains.txt
```

From Savitar:
```shell
sudo gobuster vhost -u [http://ip] -w /home/rhaenesis/Tools/SecLists/Discovery/DNS/subdomains-top1million-5000.txt -o gobuster_subdomains.txt --append-dom -t 200 -r -o subdoms.txt
```
