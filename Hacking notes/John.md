
For encrypted zips we can use zip2john
```
zip2john filename > filename.hash
```

And then you just run john
```
john filename.hash
```

- **Cracking MD5 hashes**
	- sudo john --format=Raw-MD5 --wordlist=/usr/share/wordlists/rockyou.txt [file]


- **Private ssh key to passcode:**
	- ssh2john.py [ssh_key] > [new_file_with_hash]
	- Then you crack the hash with john --format=ssh [new_file_with_hash]
	- Then you connect to ssh doing this: ssh -i [ssh_key] username@[ip] (make sure you chmod 600 the ssh_key)
	- And then you use the password you cracked from the hash using john.

[[Brute force]]
[[Hashing]]
[[Encryption]]