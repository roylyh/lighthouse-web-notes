# Roy's notes

## Clause order
(keywords order in postgres)

The main clauses of a SELECT statement in PostgreSQL are written in the following order:

**SELECT
FROM
JOIN
WHERE
GROUP BY
HAVING
WINDOW
ORDER BY
OFFSET
LIMIT**

## Postgres
**startpostgres** start postgres server  
**psql**
There are 3 commands you need to know once PostgreSQL is installed:

**sudo service postgresql status** for checking the status of your database.
**sudo service postgresql start** to start running your database.  
**sudo service postgresql stop** to stop running your database.

[17 Practical psql Commands That You Don’t Want To Miss](https://www.postgresqltutorial.com/postgresql-administration/psql-commands/)  
\c connect to a database  
\l list available databases  
\dt list available tables  
\d table_name describe a table  
\df list available functions  
\du list users and their roles  
\i filename execute psql commands from a file  
\\? get help  
\time turn on query execution time  
\q quit psql

## SQL
JOIN  
PostgreSQL supports inner join, left join, right join, full outer join, cross join, natural join, and a special kind of join called self-join. (self-join with alias)  
[PostgreSQL Joins](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-joins/)  
![join tables](https://github.com/roylyh/lighthouse-web-notes/blob/f6a3af66ccc16049ff9fa6e89ffb7035328eff19/docs/jointables.PNG)
[Visual explanation of sql join](https://blog.codinghorror.com/a-visual-explanation-of-sql-joins/)

## Explain
Known as a Query Plan or Execution Plan, EXPLAIN shows us information such as which tables are scanned, and which indexes are used for JOINs.  
[postgresql - explain](https://www.postgresql.org/docs/9.0/sql-explain.html)

## Self Join
In this activity we will practice JOINing a table to itself.(SQLZoo)