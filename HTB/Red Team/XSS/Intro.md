
[[XSS Cross-Site Scripting]] is among the most common types of web app vulns.

When a vulnerable web app does not properly sanitize user input, a malicious user can inject extra JavaScript code in an input field so once another user views the same page, they unknowingly execute the malicious JavaScript.
XSS vulns are solely executed on the client-side and hence do not directly affect the [[Back End Servers]]. Low impact + high probability = medium risk.

Types of XSS

- [[Stored XSS]] (persistent)
	- This is the most critical type, which occurs when a user input is stored on the back end database and then displayed upon retrieval.
- [[Reflected XSS]] (non persistent)
	- Occurs when user input is displayed on the page after being processed by the back end server, but without being stored.
- [[DOM XSS]] 
	- Non persistent. Occurs when user input is directly shown in the browser and is completely processed on the client side without reaching the back end server parameters or anchor tags.
