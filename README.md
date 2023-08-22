
<!---

docs: update README.md
-->


Here I will explore SQL concepts, working with the Sakila database.


# CRUD
## Create

```sql
-- CREATE, INSERT DATA
INSERT INTO language (name)
VALUES("Portuguese");
```


## Select 
```sql
-- SELECT TABLE FILM
SELECT * FROM film;
```
SET SQL_SAFE_UPDATES = 0;

- ### Select specific columns
```sql
-- SELECT COLUMNS: title description of table film
SELECT title, description FROM film;
```

- ### Select equal
```sql
-- SELECT TABLE FILM WITH LENGTH...
SELECT * FROM film
WHERE length = 126
```



## Update
```sql
-- UPDATE DATA 
UPDATE staff
SET picture = 'https://files.tecnoblog.net/wp-content/uploads/2019/02/thispersondoesnotexist.jpg'
WHERE first_name = 'Mike' 
```
SET SQL_SAFE_UPDATES = 0;
## Delete

```sql
-- DELETE DATA 
DELETE FROM language
WHERE name = "Portuguese"
```
# ORDER BY
```sql
--- ORDER BY name
SELECT * FROM category
ORDER BY name DESC;
```

```sql
--- ORDER BY category_id
SELECT * FROM category
ORDER BY category_id DESC;
```


# JOIN
```sql
SELECT staff.first_name, payment.*
FROM staff
JOIN payment ON staff.staff_id = payment.staff_id
```
