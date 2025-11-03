
## Use of [[SQL]] in Web Applications
Firs, let us see how web applications use databases [[MySQL]], in this case, to store and retrieve data. Once a [[DBMS]] is installed and set up on the [[Back end]] server and is up and running, the [[web application]] can start utilizing it to store and retrieve data.

For example, within a PHP web app we can connect to our database and start using the MySQL database through MySQL syntax, right within PHP as follows:

```php
$conn = new mysqli("localhost", "root", "password", "users");
$query = "select * from logins";
$result = $conn->query($query);
```
Then, the query's output will be stored in $result and we can print it to the page or use it in any other way. 
This will print all returned results of the SQL query in new lines:
```php
while($row = $result->fetch_assoc() ){
	echo $row["name"]."<br>";
}
```
*If we use user-input within an SQL query, and if not securely coded, it may cause a variety of issues, like SQL Injection vulnerabilities.*


## What is an injection?
[[SQLi]]
[[SQL Injection]]
Injection occurs when an application misinterprets user input as actual code rather than a string, changing the code flow and executing it. This can occur by escaping user-input bounds by injecting a character `'` and then writing code to be executed, like [[JS]] or SQL in [[SQL injections]]. Unless the user input is sanitized, it is very likely to execute the injected code and run it.

## SQL Injection
An SQL injection occurs when user-input is inputted into the SQL query string without properly sanitizing or filtering the input. 

```php
$searchInput = $_POST['findUser'];
$query = "select * from logins where username like '%$searchInput'";
$result = $conn->query($query);
```

In typical cases, the `searchInput` would be inputted to complete the query returning the expected outcome. Any input we type goes into the following SQL query:
```sql
SELECT * FROM logins WHERE username LIKE '%$searchInput'
```
So if we input admin it becomes %admin. In this case, if we write any SQL code, it would just be considered as a search term. For example, if we input SHOW DATABASES;, it would be executed as %SHOW DATABASES; and the web app will search for usernames similar to SHOW DATABASES;. However as there is no sanitization, in this case *we can add a single quote `'`, which will end the user-input field and after it we can write actual SQL code.*

```php
'%1'; DROP TABLE users;'
```

For the sake of simplicity, we added another SQL query after a semi-colon. Though this is actually not possible with MySQL, it is possible with [[MSSQL]] and [[PostgreSQL]]. 

## Syntax Errors
The previous example of SQLi would return an error. This is because of the last trailing character, where we have a single extra quote that is not closed, which causes an SQL syntax error when executed:
```sql
select * from logins where username like '%1'; DROP TABLE users;'
```
In this case, we had only one trailing character as our input from the search query was near the end of the SQL query. However, the user input usually goes in the middle of the SQL query and the rest of the original SQL query comes after it.

To have a successful injection we must ensure that the newly modified SQL query is still valid and does not have any syntax errors after our injection.


## Types of SQL Injections

SQL Injections are categorized based on how and where we retrieve their output:
![[Pasted image 20250101211451.png]]
In simple cases, the output of both the intended and the new query may be printed directly on the front end and we can directly read it. This is known as [[In-band SQL Injection]] and it has two types: [[Union Based]] and [[Error Based]].

- Union based
	- We may have to specify the exact location, i.e. column, which we can read, so the query will direct the output to be printed there.
- Error based
	- It is used when we can get PHP or SQL errors in the front end so we may intentionally cause an SQL error that returns the output of a query.

In more complicated cases we may not get the output printed so we may utilize SQL logic to retrieve the output character by character. This is known as a [[Blind SQL Injection]] and it also has two types: [[Boolean Based]] and [[Time Based]].

- Boolean based
	- We can use SQL conditional statements to control whether the page returns any output at all.
- Time Based
	- We use SQL conditional statements that delay the page response if the conditional statement returns true using the Sleep() function.

Finally, in some cases, we may not have direct access to the output whatsoever, so we may have to direct the output to a remote location, i.e. DNS record, and then attempt to retrieve it from there. This is known as [[Out of Band SQL Injection]].