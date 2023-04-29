# Roy's note

## LightBnB

## Data Definition Language
**Data Types** SMALLINT, INTEGER, BIGINT, DECIMAL, NUMERIC, REAL, DOUBLE, SMALLSERIAL, SERIAL, BIGSERIAL.  
[Data types of postgreSQL](https://www.postgresql.org/docs/9.3/datatype.html)

** Altering a Table** 
[PostgreSQL ALTER TABLE](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-alter-table/)

keyword: Removing a Table; NULL; Default Values; AUTO INCREMENTING / SERIAL; Foreign Keys;

Quick Reference
- Primary key column:
  - Use the name id and then SERIAL PRIMARY KEY.
- Foreign key columns:
  - Add _id to the singular name of the column you are referencing.
  - If the primary key is SERIAL, then the foreign key should be INTEGER.
  - You also should create the foreign key with REFERENCES table_name(id) ON DELETE CASCADE.
- Names, emails, usernames and passwords can all be stored as VARCHAR(255). Students to cohorts would be cohort_id. The type would be INTEGER .
- Dates would use the DATE type. If we needed date and time, use TIMESTAMP.
- Numbers:
  - We will use INTEGER to represent most numbers. There are other sizes of integers as well.
  - SMALLINT -32,768 to 32,767 (thirty-two thousand)
  - INTEGER -2,147,483,648 to 2,147,483,647 (two billion)
  - BIGINT -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 (nine quintillion)
  - SERIAL 1 to 2,147,483,647 (auto incrementing)
- Dates, Phone Numbers & Currency
  - Become familiar with the ISO 8601 date formatting standard. The string '2018-02-12' uses this format to represent 'February 12th, 2018'. Year, month and then day. Dates should be stored consistently. Apply timezones and formatting when displayed to the user.
  - Store phone numbers as VARCHAR, there are so many possible formats. The number 214 748 3647 hits our INTEGER limit.
  - Store currency as an integer representing cents. Use a BIGINT if you need values over $21 million dollars.

The SQL commands that let us interact with our data are sometimes referred to as **Data Manipulation Language (DML)** These include:
- SELECT: get data from tables.
- INSERT: add rows to a table.
- UPDATE: update rows within a table.
- DELETE: delete rows from a table.

## Node Postgres
[Node postgres](https://node-postgres.com/)

keyword:   
.gitignore https://raw.githubusercontent.com/github/gitignore/master/Node.gitignore  
psql -h localhost -p 5432 -U vagrant bootcampx  

## Pools and Clients
However, using a Pool is the preferred way to query with node-postgres. A Pool will manage multiple client connections for us which we don't really need to worry about right now. Just know that either could be used, but Pool is preferred.
https://node-postgres.com/features/pooling#pooling  

## SQL injection attacks
pool.query(queryString, values);

## Lighthouse Bnb
The database.js is responsible for all queries to the database. It doesn't currently connect to any database, all it does is return data from .json files.  
They all return promises to simulate real world code as all of our database queries will be using promises.

## SQL
Using NULL & Numberic
