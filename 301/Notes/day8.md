# Day 8
#### 6/10/20

# SQL
- not a database
- how we talk to relational databases

## To start the database
- pc - sudo service postgresql start
- mac - brew services start postgres

## What is a database
- A place to store data

## QUERIES
- SELECT
- INSERT
- UPDATE
- DELETE

- All students who like coffee - `SELECT * FROM students WHERE favorite_drink = 'coffee';`
- All the names of the student - `SELECT name FROM students;`
- All the favorite_foods of the students - `SELECT favorite_food FROM students;`
- All the students who like Thai food - `SELECT * FROM students WHERE favorite_food='Thai';`


- sql is not case sensitive. the capitals of the SELECT is convention.
### SELECT STATMENTS
1. what do we want to do - SELECT
1. which columns are at play - 
1. what table are we working from - [tablename]
1. how should we filter it - WHERE

### INSERT
`INSERT INTO students(name, favorite_drink,) VALUES ('Laura', 'Tea');`

- formula
    - INSERT INTO [tableName] (column-name, another-column-name) VALUES (value, value);

## Postgres - port 5432
- `CREATE DATABASE [name]`
- \c to connect to the database
- \q to quit psql
- spql [databaseName]
## Database
- databases holds tables
- tables holds data
## DROP DATABASE - deletes the database perminantly.
- \dt to see the tables in a database

## Setting up the database in VSCode
```SQL
DROP TABLE IF EXISTS people;

CREATE TABLE people(
    id SERIAL PRIMARY KEY,
    first_name VARCHAR(255),
    last_name VARCHAR(255)
);

INSERT INTO people (first_name, last_name) VALUES ('Diane', 'Stephani')
```

- In the terminal not in psql `psql -f schema.sql -b test` - connects file to database
    - `-f` file
    - `-d` database
- spql: `SELECT * FROM people;`

- schema file does what you can do in the terminal

## pg
```JavaScript
const client = new pg.Client(process.env.DATABASE_URL);

client.on('error', err=> console.error(err));
client.connect()
```

```JavaScript
client.query(SQL query, safe values).then().catch();
```

### Safe values
- replace values with $1, $2, $3
    - do not start with $0
- `let sql = 'INSERT INTO people (first_name, last_name) VALUES ($1, $2);`
- `let safeValues = ['bob', 'dylan'];`
- `client.query(sql, safeValues).then().catch()`

- `postgres://USER:PASSWORD@localhost:5432/DBNAME`
    - postgre user name and password

- `heroku pg:psql -f schema.sql -a [heroku_app_name]`


- ROW COUNT if 0 sqlResult.rowcount