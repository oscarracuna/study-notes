
There are two types of [[Non-persistent XSS]] vulnerabilities:

- [[Reflected XSS]]
	- Gets processed by the [[Back end]] server.
- [[DOM-based XSS]]
	- Completely processed on the client-side and never reaches the back-end.

[[Non-persistent XSS]] vulnerabilities are temporary and are not persistent through *page refreshes* so it won't affect other users who visit the page.

[[Reflected XSS]] occur when our input reaches the back-end server and gets returned to us without being filtered or sanitized.

on.error or message XSS payloads are temporary so we can use them to see how they execute. 

## But if the XSS vulnerability is Non-Persisten, how would we target victims with it?

This depends on which [[HTTP]] request is used to send our input to the server. We can check this through Firefox Developer Tools (Or any browser's dev tools lol) -> Network tab.

![[Pasted image 20241208122117.png]]
This shows the request was a GET request. These request send their parameters and data as part of the URL. *So, to target a user, we can send them a URL containing our payload.* 