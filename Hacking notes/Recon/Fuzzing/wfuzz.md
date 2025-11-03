
## For domains:
```
sudo wfuzz -c -w /home/rhaenesis/Tools/SecLists/Discovery/Web-Content/big.txt -H "Host: [test.com]/FUZZ" --hc 404 -t 100 [test.com]
```
Don't forget ``--hw`` 

## For subdomains:
```
sudo wfuzz -c -w /home/rhaenesis/Tools/SecLists/Discovery/DNS/subdomains-top1million-110000.txt -H "Host: FUZZ.[test.com]" --hc [status-code-to-avoid] --hw [wordcount] -t 100 [test.com]
```


Other sources are ~/Tools/SecLists/Discovery