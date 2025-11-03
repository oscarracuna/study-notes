

Hypertext Transfer Protocol Secure (HTTPS)
- Contrary to HTTP, data here is NOT transmitted in clear text. which counters Man in the middle attacks.
- All communications are transferred in an encrypted format.
	- Although the data transferred may be encrypted, the *request* may still reveal the visited URL if it contacted a clear-text DNS server.
- ![[Screenshot_2024-05-05_16-03-21.png]]
- If we were to type http instead of https to visit a website that *enforces* https, the browser attempts to resolve the domain and redirects the user to the web server hosting the target website.
	- A request is sent to port 80 first, the server detects it and redirects to the secure port which is 443 via *301 Moved Permanently* response code.