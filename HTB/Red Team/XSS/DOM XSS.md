
This is also a [[Non-persistent XSS]] vulnerability. While [[Reflected XSS]] sends the input data to the [[Back end]] server through HTTP requests. [[DOM XSS]] is completely process on the client-side through [[JavaScript]]. It occurs when JavaScript is used to change the page source through thee [[Document Object Model]] ([[DOM]]).

## [[Source]] and [[Sink]]
To further understand the nature of the DOM-based XSS vuln, we must understand the concept of the Source and Sink of the object displayed on the page. The [[Source]] is the JS object that makes the user input and it can be any input parameter like a URL parameter or an input field.
On the other hand, the [[Sink]] is the function that writes the user input to a DOM object on the page. If the Sink function does not properly sanitize the user input, it would be vulnerable to an XSS attack. Some of the commonly used JS functions to write DOM objects are:

- document.write()
- DOM.innerHTML
- DOM.outerHTML

Furthermore, some of the jQuery library functions that write to DOM objects are:

- add()
- after()
- append()

If a Sink function writes the exact input without any sanitization and no other means of sanitization were used, then we know that the page should be vulnerable to XSS.

For example, the innerHTML function does not allow the use of `<script>` tags within it as a security feature, but there are other [[XSS Payloads]] we use that do not contain the script tag:

```html
<img src="" onerror=alert(window.origin)>
```

This payload creates a new HTML image object which has an onerror attribute that can execute JS code when the image is not found. 