
Now that we understand how to use the MySQL utility and create databases and tables, let us look at some of the essential SQL statements and their uses.

## INSERT statement
The [[INSERT]] statement is used to add new records to a given table. The statement following the below syntax:

```SQL
INSERT INTO table_name VALUES (column1_value, column2_value, column3_value, ...);
```

```SQL
INSERT INTO logins VALUES(1, 'admin', 'p@ssw0rd', '2020-07-02');
```
This shows how to add a new login to the logins table, with appropriate values for each column. However, we can skip filling columns with default values, such as id and date_of_joining. This can be done by specifying the column names to insert  values into a table selectively:

```SQL
INSERT INTO table_name(column2, column3, ...) VALUES (column2_value, column3_value, ...);
```
Skipping columns with the 'NOT NULL' constraint will result in an error, as it is a required value.

We can also insert multiple records at once by separating them with a comma:

```sql
INSERT INTO logins(username, password) VALUES ('john', 'john123!'), ('tom', 'tom123!');
```

## SELECT statement
This statement can also be used for many other purposes, which we will come across later. The general syntax to view the entire table is as follows:

```SQL
SELECT * FROM table_name;
```

Is possible to view data present in a specific column as well:

```sql
SELECT column1, column2 FROM table_name;
```


## DROP statement
We can use DROP to remove tables and databases from the server.

```sql
DROP TABLE logins;
```
The DROP statement will permanently and completely delete the table with no confirmation so it should be used with caution.

## ALTER statement
We can use ALTER to change the name of any table and any of its fields or to delete or add a new column to an existing table. The below example adds a new column `newColumn` to the logins table using ADD:
```Sql
ALTER TABLE logins ADD newColumn INT;
```
To rename a column we can use the RENAME COLUMN:
```sql
ALTER TABLE logins RENAME COLUMN newColumn TO oldColumn;
```
We can also change a column's datatype with MODIFY:
```sql
ALTER TABLE logins MODIFY oldColumn DATE;
```
Finally we can drop a column by using DROP:
```sql
ALTER TABLE logins DROP oldColumn;
```


## UPDATE statement
While ALTER is used to change a table's properties, the UPDATE statement can be used to update specific records within a table, based on certain conditions. Its general syntax is:

```sql
UPDATE table_name SET column1=newvalue1, columnn2=newvalue2, ... WHERE <condition>;
```
We can specify the table name, each column and its new value, and the condition for updating records. 
```sql
UPDATE logins SET password = 'change_password' WHERE id > 1;
```
We have to specify the 'WHERE' clause with UPDATE in order to specify which records get updated. 

To change "cd" into a database you can do the following:
```sql
USE table_name;
```
And to display your current database you can do:
```sql
SELECT DATABASE();
```
