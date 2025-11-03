It's a numeric value of a fixed length that uniquely identifies data.
A hash value is the result of a hashing algorithm.
	For example:
	- MD5
	- SHA1
	- SHA2

The hash values are usually used to gain insight into a specific malware sample or suspicious file. For example, comparing the hash values of 1 file prior and post upload to a server to determine when it got infected. 




-----IP address-----
They are used to identify a device connected to a network.

IP addresses have the color green in the Pyramid of Pain

Domain names:
	They simply map an IP address to a string of text.
	- Can contain a domain and top-level domain (evilcorp.com)
	- Or a subdomain followed by a top-level domain (tryhackme.evilcorp.com).
Attackers will have a harder time changing domains -not as easy as IP addresses- since they need to buy the domain, register and modify the DNS records. But APIs and DNS providers loose standars make it easier for them.

[[punycode]]
- A way of converting words that cannot be written in ASCII into Unicode ASCII encoding.

[[URL SHortener]]
- It's a tool that creates a short and unique URL that will redirect to the specific website specified during the initial step of setting up the URL shortener link.

For example:
- bit.ly
- goo.gl
- ow.ly
- s.id
- smarturl.it
- tiny.pl
- tinyurl.com
- x.co


Host artifacts
- Traces or observables that attackers leave on the system, such as registry values, suspicious process execution, attack patterns or IOCs or anything exclusive to the current threat.

**Fast flux** It's a DNS technique used by botnets to hide phishing, web proxyin, malware delivery and malware communication *behind* compromised hosts acting as proxies. --> Having multiple IP addresses associated with a domain name, which is constantly changing. 