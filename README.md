
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

## Distinct
```sql
SELECT country_id, city FROM city
ORDER BY country_id


SELECT DISTINCT country_id FROM city
ORDER BY country_id
```



# AS
```sql
-- RENAME COLUMNS
SELECT title as Título, description as Descrição FROM film
--or

SELECT title as "Título do Filme", description as Descrição FROM film
```
# COMPARASION

- ## > = != <
```sql
-- GREATER-THAN SIGN
SELECT * FROM film
WHERE rental_duration > 6;
```
```sql
-- GREATER-THAN SIGN or EQUAL
SELECT * FROM film
WHERE length <= 60;
```

```sql
SELECT * FROM customer
WHERE active != 1
```
- ## OR NOT

```sql
SELECT * FROM film
WHERE rental_duration = 5 OR length>90
```

```sql
SELECT * FROM film
WHERE rental_duration = 7;
```

```sql
SELECT * FROM film
WHERE NOT rental_duration = 7;
```

```sql
SELECT * FROM rental
WHERE customer_id='239' and NOT inventory_id ='2346';
```


# IN

```sql
SELECT * FROM film
WHERE length ='30'
OR length='60'
OR length='120';
```

```sql
SELECT * FROM film
WHERE length IN (60,90,120);
```

# BETWEEN

```sql
SELECT * FROM film
WHERE length BETWEEN 50 AND 55;
```

# ORDER BY

```sql
--- ORDER BY name
SELECT * FROM category
ORDER BY name DESC;
```

```sql
SELECT * FROM film
WHERE replacement_cost BETWEEN 20 AND 25
ORDER BY replacement_cost DESC;
```


```sql
--- ORDER BY category_id
SELECT * FROM category
ORDER BY category_id DESC;
```
# LIKE

```sql
SELECT * FROM film
WHERE title LIKE("%PHOBIA%")
```

```sql
SELECT * FROM film
WHERE title LIKE("%ts%")
```

```sql
SELECT * FROM customer
WHERE first_name LIKE ("ERI%")
```

```sql
SELECT * FROM customer
WHERE last_name LIKE ("%TS")
```

# REGEXP

```sql
SELECT * FROM film
WHERE title REGEXP("^da")
```

```sql
SELECT * FROM film
WHERE title REGEXP("ra$")
```


# JOIN
```sql
SELECT staff.first_name, payment.*
FROM staff
JOIN payment ON staff.staff_id = payment.staff_id
```

