
**Some of the most common vulnerabilities and part of the [[OWASP Top 10

**[[Broken Authentication/Access control]]**
Broken authentication refers to vulnerabilities that allow attackers to bypass authentication functions. For example, login without having a valid set of credentials or allow a normal user to become administrator.

Broken access control refers to vulnerabilities that allow attackers to access pages and features they should not have access to.

[[Malicious File Upload]]
We may upload a malicious script if the web has a file upload feature that does not correctly validate the files.
Even if there are checks and attempts to validate the uploaded files, the checks can often be bypassed, for example, with double extension files(shell.php.jpg).

[[Command Injection]]
Injection or execution of arbitrary commands.
Devs may not properly sanitize user input or use weak tests to do so, allowing attackers to bypass any checks or filtering put in place and execute their commands.

[[SQL Injection]] ([[SQLi]])
Similar to command injection, this vuln occurs when the web app executes a SQL query, including a value taken from user-supplied input.