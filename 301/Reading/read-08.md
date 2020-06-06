# Read: 08 - SQL
#### 6/6/20

- [SQLBolt](https://sqlbolt.com/) 1-4, 13-18
- [W3 Schools SQL](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all)
- [Primer on SQL](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all)
- [SQL Cheatsheet](http://www.cheat-sheets.org/sites/sql.su/)

## SQL
### SELECT queries
- SELECT [Column],[another_column] FROM [TableName]; dont forget the `;`
### Queries with constraints
- `WHERE` clause
```SQL
SELECT column, another_column
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR ...;
```

- Most common Operators
- =, !=, <, <=, >, >=
- BETWEEN ... AND ...
- NOT BETWEEN .. AND ...
- IN (...) - number exist in a list
- NOT IN (...) - a number doesn't exist in a list

- LIKE and NOT LIKE
- LIKE "%ABC%" - match a sequence of zero or more characters
- LIKE "AN_" - match a single character.
- IN(...)
- NOT IN(...)

### Filtering and sorting Query results
- DISTINCT - a way to discard duplicate column values
- Ordering results
    - ORDER BY ASC/DESC - give the results in ascending or descending order.
- Limiting results to subset
    - LIMIT - will reduce the number of rows to return
    - OFFSET - specify where to start counting

### Inserting Rows
- A Schema as a column structure of a table
- INSERT INTO [tableName]
- VALUES (data, data ,data),
        (data, data, data);
```SQL
INSERT INTO mytable
VALUES (value_or_expr, another_value_or_expr, …),
       (value_or_expr_2, another_value_or_expr_2, …),
       …;
```
### Updating Rows
- UPDATE
- SET
- WHERE - don't forget this or it'll update the whole table
- Tricks to take care   
    - Always write the constraint first and test it in a SELECT query to make sure you are updating the correct rows.
``` SQL
UPDATE mytable
SET column = value_or_expr, 
    other_column = another_value_or_expr, 
    …
WHERE condition;
```
### Deleting Rows
``` SQL
DELETE FROM mytable
WHERE condition;
```
> TAKE CARE YOU CAN DELETE THE WHOLE TABLE IF NOT CAREFUL!!!!!!!!!!!!!!

### Creating Tables
``` SQL
CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);
```

Data type	| Description
--- | ---
INTEGER, BOOLEAN | The integer datatypes can store whole integer values like the count of a number or an age. In some implementations, the boolean value is just represented as an integer value of just 0 or 1.
FLOAT, DOUBLE, REAL | The floating point datatypes can store more precise numerical data like measurements or fractional values. Different types can be used depending on the floating point precision required for that value.
CHARACTER(num_chars), VARCHAR(num_chars), TEXT | The text based datatypes can store strings and text in all sorts of locales. The distinction between the various types generally amount to underlaying efficiency of the database when working with these columns. Both the CHARACTER and VARCHAR (variable character) types are specified with the max number of characters that they can store (longer values may be truncated), so can be more efficient to store and query with big tables.
DATE, DATETIME | SQL can also store date and time stamps to keep track of time series and event data. They can be tricky to work with especially when manipulating data across timezones.
BLOB | Finally, SQL can store binary data in blobs right in the database. These values are often opaque to the database, so you usually have to store them with the right metadata to requery them.


Constraint | Description
--- | ---
PRIMARY KEY | This means that the values in this column are unique, and each value can be used to identify a single row in this table.
AUTOINCREMENT | For integer values, this means that the value is automatically filled in and incremented with each row insertion. Not supported in all databases.
UNIQUE | This means that the values in this column have to be unique, so you can't insert another row with the same value in this column as another row in the table. Differs from the `PRIMARY KEY` in that it doesn't have to be a key for a row in the table.
NOT NULL | This means that the inserted value can not be `NULL`.
CHECK (expression) | This allows you to run a more complex expression to test whether the values inserted are valid. For example, you can check that values are positive, or greater than a specific size, or start with a certain prefix, etc.
FOREIGN KEY |This is a consistency check which ensures that each value in this column corresponds to another value in a column in another table. For example, if there are two tables, one listing all Employees by ID, and another listing their payroll information, the `FOREIGN KEY` can ensure that every row in the payroll table corresponds to a valid employee in the master Employee list.

### Altering Tables
- Adding columns
``` SQL
ALTER TABLE mytable
ADD column DataType OptionalTableConstraint 
    DEFAULT default_value;
```
- Removing Columns
``` SQL
ALTER TABLE mytable
DROP column_to_be_deleted;
```
- Renaming the Table
``` SQL
ALTER TABLE mytable
RENAME TO new_table_name;
```
### Dropping Tables
- DROP TABLE removes the table and it's schema from the database
    - REMOVE only removes the data not the schema
```SQL
DROP TABLE IF EXISTS mytable;
```

