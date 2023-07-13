 Here I will explore SQL concepts, working with the Sakila database.


# CRUD DATA
## Create

```sql
-- CREATE, INSERT DATA
INSERT INTO language (name, )
VALUES("Portuguese");
```


## Select
```sql
-- SELECT DATA
SELECT description, title FROM film;
```

SET SQL_SAFE_UPDATES = 0;

## Update
```sql
-- UPDATE DATA 
UPDATE staff SET picture = 'https://files.tecnoblog.net/wp-content/uploads/2019/02/thispersondoesnotexist.jpg' WHERE first_name = 'Mike' 
```

## Delete

```sql
-- DELETE DATA 
DELETE FROM language WHERE name = "Portuguese"
```

