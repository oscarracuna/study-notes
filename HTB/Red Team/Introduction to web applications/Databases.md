Web apps use back end [[database]]s to store various content and information related to the web application.
There are many different tupes of databases, each of which fits a certain type of use.

**Things developers look for in databases**:
- Speed in storing and retrieving data
- Size when storing large amount of data
- Scalability
- Cost

**[[Relational SQL]]**
Relational [[SQL]] databases store their data in tables, rows and columns. Each table can have unique keys, which can link tables together and create relationships between tables.

For example, we can have a **users** table in a relational database containing columns like **id**, **username**, **first_name**, **last_name**, and so on. The **id** can be uses as the table key. And in another table called **posts**, may contain posts made by all users, with columns like **id**, **user_id**, **content**, and so on.

![[Pasted image 20240601154713.png]]
We can now link the **id** from the **users** table to the **user_id** in the **posts** table to easily retrieve the user details for each post without having to store all user details with each post.

The relationship between tables within a database is called a **Schema**.

Some of the most common relational databases are:
- [[MySQL]]
- [[MSSQL]]
- [[Oracle]]
- [[PostgreSQL]]

**Non-relational (NoSQL)**

These do not use tables, rows, columns, primary keys, relationships or schemas. Instead, a [[NoSQL]] database stores data using various storage models depending on the type of data stored.

Due to the lack of a defined structure for the database, NoSQL databases are very scalable and flexible. When dealing with datasets that are not very well defined and structured, a **NoSQL** database would be the best choice.

There are 4 common storage models for **NoSQL** databases:
- Key-Value (uses JSON or XML typically)
- Document-Based
- Wide-Column 
- Graph

Within a PHP app, once **MySQL** is up and running, we can connect to the database server with:

```php
$conn = new mysqli("localhost", "user", "pass");
```

And then we can create a new database with:
```php
$slq = "CREATE DATABASE database1";
$conn->query($sql)
```

After that, we can connect to our new database and start using the MySQL database though MySQL syntax.
```php
$conn = new mysqli("localhost", "user", "pass", "database1");
$query = "select * from table_1";
$result = $conn->query($query);
```
Web applications usually use user-input when retrieving data. For example, when a user uses the search function to search for other users, their search input is passed to the web application, which uses the input to search withing the database.
```php
$searchInput = $_POST['findUser'];
$query = "select * from users where name like '%$searchInput%'"
$result = $conn->query($query)
```
Finally, the web app sends the result back:
```php
while($row = $result->fetch_assoc() ){
	echo $row["name"]."<br>";
}
```
