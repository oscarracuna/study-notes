
Most modern web apps utilize a database structure on the [[Back end]]. Such databases are used to store and retrieve data related to the web application, from actual web content to user information and content. To make the web apps dynamic, the web app has to interact with the database in real-time. As HTTP(s) requests arrive from the user, the web app back end will issue *queries* to the database to build the response. These queries can include information from the HTTPS request or other relevant information.
![[Pasted image 20241229135553.png]]
When user-supplied info is used to construct the query to the database, malicious users can trick the query into being used for something other than what the original programmer intended, providing the user access to query the database using an attack know as [[SQL injection]] ([[SQLi]]). 

SQL injection refers to attacks against relational databases such as [[MySQL]] (whereas injections against non-relational databases, such as [[MongoDB]], are NoSQL injections).

## SQL Injection (SQLi)
Many types of injection vulnerabilities are possible within web apps, such as HTTP injection, code injection, and command injection. The most common example, however, is SQL injection. A SQL injection occurs when a malicious user attempts to pass input that changes the final SQL query sent by the web app to the database, enabling the user to perform other unintended SQL queries directly against the database.

There are many ways to accomplish this. To get a SQLi to work, the attacker must first inject SQL code and then subvert the web app logic by changing the original query or executing a completely new one. First, the attacker has to inject code outside the expected user input limits, so it does not get executed as simple user input. IN the most basic case, this is done by injecting a single quote `'` or a double quote `"` to escape the limits of user input and inject data directly into the SQL query.

Once an attacker can inject, they have to look for a way to execute a different SQL query. This can be done using SQL code to make up a working query that executes both the intended and the new SQL queries. There are many ways to achieve this, like using [[stacked queries]] or using [[Union queries]]. Finally, to retrieve our new query's output, we have to interpret it or capture it on the web app's front end.