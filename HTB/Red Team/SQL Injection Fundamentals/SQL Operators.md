
Sometimes, expressions with a single condition are not enough to satisfy the user's requirement. For that [[SQL]] supports [[logical operators]] to use multiple conditions at once. The most common are AND, OR, and NOT.

## AND operator
The AND operator takes in two conditions and returns true or false based on their evaluation:
```sql
SELECT 1 = 1 AND 'test' = 'test';

+---------------------------+
| 1 = 1 AND 'test' = 'test' |
+---------------------------+
|                         1 |
+---------------------------+
1 row in set (0.00 sec)

```

```sql
SELECT 1 = 1 AND 'test' = 'abc';

+--------------------------+
| 1 = 1 AND 'test' = 'abc' |
+--------------------------+
|                        0 |
+--------------------------+
1 row in set (0.00 sec)
```
In [[MySQL]], any non-zero value is considered true and it usually returns the value 1 to signify true. Zero is considered false. 

## NOT operator
Simply toggles a boolean value i.e. true is converted to false and vice versa.

```sql
SELECT NOT 1 = 1;

+-----------+
| NOT 1 = 1 |
+-----------+
|         0 |
+-----------+
1 row in set (0.00 sec)
```

```sql
SELECT NOT 1 = 2;

+-----------+
| NOT 1 = 2 |
+-----------+
|         1 |
+-----------+
1 row in set (0.00 sec)
```


## Multiple Operator Precedence
SQL supports various other operations such as addition, division as well as bitwise operations. Thus, a query could have multiple expressions with multiple operations at once.

```powershell
Division (/), multiplication (*), modulus (%)

Addition (+) and substraction (-)

Comparission (=, >, <, <=, >=, !=, LIKE)

NOT (!)

AND (&&)

OR (||)
```
Operations at the top are evaluated before the ones at the bottom of the list.

```sql
select * from logins where username != 'tom' AND id > 3 - 2;

+----+---------------+------------+---------------------+
| id | username      | password   | date_of_joining     |
+----+---------------+------------+---------------------+
|  2 | administrator | adm1n_p@ss | 2020-07-03 12:03:53 |
|  3 | john          | john123!   | 2020-07-03 12:03:57 |
+----+---------------+------------+---------------------+
2 rows in set (0.00 sec)
```
