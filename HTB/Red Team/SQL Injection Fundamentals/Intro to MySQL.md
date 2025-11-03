
## Structured Query Language (SQL)
[[SQL]] syntax can differ from one [[RDBMS]] to another. However, they all are required to follow the [[ISO]] standard for Structured Query Language. SQL can be used to perform the following actions:

- Retrieve data
- Update data
- Delete data
- Create new tables and databases
- Add or remove users
- Assign permissions to these users

## Command Line
The [[MySQL]] utility is used to authenticate to and interact with MySQL/MariaDB database. The -u flag is uses to supply the username and the -p flag is for the password. The -p flag should be passed empty, so we are prompted to enter the password and o not pass it directly on the command line since it could be stored in clear text in the bash_history file.
```bash
mysql -u root -p
```

When we do not specify a host, it will default to the localhost server. We can specify a remote host and port sing the -h and -P flags.
```shell
mysql -u root -h docker.hackthebox.eu -P 3306 -p
```

MySQL expects command line queries to be terminated with a semi-colon. 
```SQL
CREATE DATABASE users;
```

![[Pasted image 20241229143309.png]]

## Tables
[[DBMS]] stores data in the form of tables. A table is made up of horizontal rows and vertical columns. The intersection of a row and a column is called a cell. Every table is created with a fixed set of columns, where each column is of a particular data type.

A data type defines what kind of value is to be held by a column. Common examples are numbers, strings, date, time and binary data.

```SQL
CREATE TABLE logins (
	id INT,
	username VARCHAR(100),
	password VARCHAR(100),
	data_of_joining DATETIME
);
```

## Table properties
Within the CREATE TABLE query,there are many properties that can be set for the table and each column. For example, we can set the id column to auto-increment using the AUTO_INCREMENT keyword, which automatically increments the id by one every time a new item is added to the table.
```sql
id INT NOT NULL AUTO_INCREMENT
```