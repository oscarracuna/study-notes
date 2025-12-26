
By now, we should have a good understanding of what an [[XSS]] vulnerability is and its different types. 

XSS Vulnerabilities are mainly linked to two parts of the web application: A source like a user input field and a [[Sink]] that displays the input data. These are the main two points that we should focus on securing, both in the [[Front end]] and in the [[Back end]].

The most importan aspect of preventing XSS vulnerabilities is proper input sanitization and validation on both, the front and back ends.

## Front end
As the front end of the web app is where most but not all of the user input is taken from, it is essential to sanitize and validate the user input on the front end using [[JavaScript]].

**Input Validation**
For example, you can validate emails with the following JS code:
```Javascript
function validateEmail(email) {
    const re = /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test($("#login input[name=email]").val());
}
```
**Personal Note**: Validating emails, or rather relying only on  regex is kinda bad, for what I've heard from programmers. The best regex to validate email is super super long so the work around would be using regex but also sending an email to that address to validate.

**Input sanitization**
In addition to input validation, we should always ensure that we do not allow any input with JS code in it by escaping any special characters. For this, the DOMPurify JS library can be used.
```Javascript
<script type="text/javascript" src="dist/purify.min.js"></script>
let clean = DOMPurify.sanitize( dirty );
```

This will escape any special characters with a backslash: \ which should help ensure that a user does not send any input with special characters which should prevent vulnerabilities like DOM XSS.

**Direct input**
Finally, we should always ensure that we never use user input directly within certain HTML tags, like:
	1. JS code `<script></script>`
	2. CSS Style code `<style></style>`
	3. Tag/Attribute fields `<div name'input'></div>`
	4. HTML comments `<--!-->`

If user input goes into any of the above examples, it can inject malicious JS code, which may lead to an XSS vulnerability. In addition to this, we should avoid using JS functions that allow changing raw text on HTML fields, like:
	1. DOM.innerHTML
	2. DOM.outerHTML
	3. docuement.write()
	4. document.writeln()
	5. document.domain

And the following jQuery functions:
	1. html()
	2. parseHTML()
	3. add()
	4. append()
	5. after()
	6. instertAfter()
	7. before()
	8. insertBefore()
	9. replaceAll()
	10. replaceWith()

As these functions write raw text to the HTML code, if any user input goes into them, it may include malicious JS code, which leads to an XSS vulnerability.