
This is the most critical type of [[XSS Cross-Site Scripting]] is the stored or persistent XSS. If or injected XSS payload gets stored in the back end database and retrieve upon visiting the page, this means that our XSS attack is persistent and may affect any user that visits the page.

[[XSS Payloads]](testing)
```javascript
<script>alert(window.origin)</script>
```

We can verify that our payload was effective by clicking CTRL U or view page source and see our payload in the page source.

Many modern web apps use cross-domain IFrames to handle user input, so that even if the web form is vulnerable to XSS, it would not be a vulnerability on the main web app. That's why we show the value of window.origin in the alert box, instead of a static value like 1. IN this case the alert box would reveal the URL it is being executed on, and will confirm which form is the vulnerable one, in case IFrame was being used.

Since most modern browsers may block the alert() JS function in specific locations, it may be handy to know a few other basic XSS payloads to verify the existence fo XSS. For example:
```html
<plaintext>
//Stops rendering the HTML code that comes after it and display it as plain text.

<script>print()</script> 
//Pops  up the browser print dialog which is unlikely to be blocked by any browsers.
```

In order to see if the payload is persistent and stored on the back end, we can refresh the page and see whether we get the alert again.