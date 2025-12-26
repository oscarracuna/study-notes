
[[HTML Injection]] vulnerabilities can often be utilized to also perform [[XSS]] attacks by injecting [[JavaScript]] code to be executed on the client-side and we can gain access to the victim's account or even the machine.

[[Types of XSS]]
- Reflected XSS
	- When user input is displayed on the page after processing, for example, search result or error message.
- Stored XSS
	- When user input is stored in the back end database and then displayed upon retrieval. Posts or comments.
- DOM XSS
	- When user input is directly shown in the browser and is written to an HTML [[DOM]] object. Vulnerable username or page

Example:

```JavaScript
#"><img src=/ onerror=alert(document.cookie)>
```
