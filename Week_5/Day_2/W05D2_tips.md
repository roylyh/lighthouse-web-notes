# Roy's Note

[sqlzoo](https://sqlzoo.net/wiki/SELECT_within_SELECT_Tutorial)

## Using NULL
COALESCE takes any number of arguments and returns the first value that is not null.  
Like || in javascript, the first not null value
```sql
COALESCE(x,y,z) = x if x is not NULL
COALESCE(x,y,z) = y if x is NULL and y is not NULL
COALESCE(x,y,z) = z if x and y are NULL but z is not NULL
COALESCE(x,y,z) = NULL if x and y and z are all NULL
```

CASE allows you to return different values under different conditions.

If there no conditions match (and there is not ELSE) then NULL is returned.
```sql
CASE WHEN condition1 THEN value1 
     WHEN condition2 THEN value2  
     ELSE def_value 
END 
```

If you want to get the result from update or insert. Add **RETURNING \*;** to the end of SQL.
```sql
INSERT INTO famous_people (first_name , last_name, birthdate) VALUES ('RR', 'LL', '2002-12-12') RETURNING *;
 id | first_name | last_name | birthdate
----+------------+-----------+------------
  4 | RR         | LL        | 2002-12-12
```

## Make your SQL safer
```sql
UPDATE users SET deleted = true WHERE id = 1 LIMIT 1;
DELETE users WHERE id = 1 LIMIT 1;
-- using transaction
BEGIN TRANSACTION;
UPDATE people SET husband = "Winston" WHERE user_id = 1;
UPDATE people SET wife = "Winnefer" WHERE user_id = 2;
COMMIT;

-- For example, here's how we can give full access to a particular user:
GRANT FULL ON TABLE users TO super_admin;
-- And here's how we can give only SELECT access to a different user:
GRANT SELECT ON TABLE users TO analyzing_user;
```

## build in function
ROUND(f,p) returns f rounded to p decimal places.
```sql
ROUND(7253.86, 0)    ->  7254
ROUND(7253.86, 1)    ->  7253.9
ROUND(7253.86,-3)    ->  7000
```
CONCAT allows you to stick two or more strings together.
```sql
CONCAT(s1, s2 ...)
```

Make union between different tables to build one single view or request
```sql
SELECT name FROM bbc WHERE name LIKE 'Z%'
UNION
SELECT name FROM actor WHERE name LIKE 'Z%'
```

CAST allows you to convert from one type to another.
```sql
CAST(expr TO type)
SELECT CAST(population/1000000 
       AS DECIMAL(8,1)) AS a
      ,population/1000000 AS b
  FROM bbc
```

We can use the word **ALL** to allow >= or > or < or <=to act over a list. For example, you can find the largest country in the world, by population with this query:
You need the condition population>0 in the sub-query as some countries have null for population.
```sql
SELECT name
  FROM world
 WHERE population >= ALL(SELECT population
                           FROM world
                          WHERE population>0)
 ```

 We can refer to values in the **outer SELECT within the inner SELECT**. We can name the tables so that we can tell the difference between the inner and outer versions.
 ```sql
 -- Find the largest country (by area) in each continent, show the continent, the name and the area:
 SELECT continent, name, area FROM world x
  WHERE area >= ALL
    (SELECT area FROM world y
        WHERE y.continent=x.continent
          AND area>0)

--List each continent and the name of the country that comes first alphabetically.
SELECT continent, name FROM world x
WHERE name <= ALL(SELECT name FROM world y WHERE x.continent = y. continent);
```

[devdoc.io](https://devdocs.io/) very good api documentation

## ERD
An Entity Relationship Diagram helps us design the schema of a database. We can use a pen and paper, a whiteboard or an online tool like draw.io.  
The key information that must be present in an ERD:
1. Names of the Entities.
2. Attributes / properties for the Entities.
3. The relations between each entity.  

There are multiple options for symbols to draw in order to identify the relationship type, here we are using a crows foot.
![ERD example](docs/ERDLHL.png)

