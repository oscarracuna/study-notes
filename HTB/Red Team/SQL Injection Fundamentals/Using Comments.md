
## Comments
Just like any other language, SQL allows the use of comments. We can use two types of line comments with MySQL `--` and `#` and an in-line comment `/**/` though it's not usually used in [[SQLi]].

```shell
SELECT username FROM logins; -- Selects usernames from the logins table 

+---------------+
| username      |
+---------------+
| admin         |
| administrator |
| john          |
| tom           |
+---------------+
4 rows in set (0.00 sec)
```

Using two dashes is not enough to start a comment so there has to be an empty space after them. Encoded it can look like `--+`

We can use the `#` as well.
```shell
SELECT * FROM logins WHERE username = 'admin'; # You can place anything here AND password = 'something'

+----+----------+----------+---------------------+
| id | username | password | date_of_joining     |
+----+----------+----------+---------------------+
|  1 | admin    | p@ssw0rd | 2020-07-02 00:00:00 |
+----+----------+----------+---------------------+
1 row in set (0.00 sec)
```
If you use the payload in the URL bar, you can't use `#` so you have to encode it as `%23`.

## [[Auth bypass]] with comments
Let's use `admin'-- ` and see:
![[Pasted image 20250107191921.png]]
