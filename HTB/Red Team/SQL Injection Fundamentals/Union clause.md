
The union clause is used to combine results from multiple `SELECT` statements. This means that through `UNION` injection, we will be able to `SELECT` and dump data from all across the [[DBMS]], from multiple tables and databases.


```shell
SELECT * FROM ports;

+----------+-----------+
| code     | city      |
+----------+-----------+
| CN SHA   | Shanghai  |
| SG SIN   | Singapore |
| ZZ-21    | Shenzhen  |
+----------+-----------+
3 rows in set (0.00 sec)


SELECT * FROM ships;

+----------+-----------+
| Ship     | city      |
+----------+-----------+
| Morrison | New York  |
+----------+-----------+
1 rows in set (0.00 sec)

```

Now let's use UNION:
```shell
SELECT * FROM ports UNION SELECT * FROM ships;

+----------+-----------+
| code     | city      |
+----------+-----------+
| CN SHA   | Shanghai  |
| SG SIN   | Singapore |
| Morrison | New York  |
| ZZ-21    | Shenzhen  |
+----------+-----------+
4 rows in set (0.00 sec)
```

*Now, the data types of the selected columns on all positions should be the same.*

## Even Columns
A `UNION` statement can only operate on `SELECT` statements with an equal number of columns.

For example, if the query is:



```sql
SELECT * FROM products WHERE product_id = 'user_input'
```

We can inject a `UNION` query into the input, such that rows from another table are returned:


```sql
SELECT * from products where product_id = '1' UNION SELECT username, password from passwords-- '
```

The above query would return `username` and `password` entries from the `passwords` table, assuming the `products` table has two columns.