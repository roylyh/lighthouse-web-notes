# Roy's Note

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