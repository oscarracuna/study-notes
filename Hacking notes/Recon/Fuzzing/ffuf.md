
### Domains
```
ffuf -c -u http://10.10.11.47/FUZZ -w ~/SecLists/Discovery/Web-Content/big.txt -fc 301
```

### Subdomains
```
ffuf -c -w ~/SecLists/Discovery/DNS/subdomains-top1million-110000.txt -u http://IP -H 'Host: FUZZ.website.com' -mc 200
```

- `-c` color.
- `-w` dictionary path.
- `-u` IP.
- `-H` must have that syntax 'Host: FUZZ.website.com'.
- `-mc` Match this response code.
