
[[WPScan]] can be used to brute force usernames and passwords. The tool uses two kinds of login brute force attacks, [[XML-RPC]] and [[wp-login]]. The latter will attempt to brute force the normal [[Wordpress]] login page, while the xmlrpc method uses the WordPress API to make login attempts through `/xmlrpc.php`. This method is preferred as it is faster.

```shell
wpscan --password-attack xmlrpc -t 20 -U admin -P /usr/share/wordlists/rockyou.txt --url http://[IP]
```
![[Pasted image 20250130182507.png]]
