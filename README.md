
<!---

docs: update README.md
-->


Here I will explore SQL concepts, working with the Sakila database.

# CREATE TABLE

```sql
CREATE TABLE users (
  user_id INT NOT NULL AUTO_INCREMENT,
  first_name VARCHAR(100),
  last_name VARCHAR(100),
  sallary INT,
  date_of_birth DATE,
  PRIMARY KEY(user_id)
)
```


# CRUD
## Create, Insert

```sql
-- CREATE, INSERT DATA
INSERT INTO users( first_name, last_name, sallary, date_of_birth)
VALUES ("Diego","Battisti", 4000, "1900-10-12")
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

# COUNT
```sql
SELECT COUNT(*) as "The movies with more than 7 days of rental" FROM film
WHERE rental_duration = 7;
```
# LIMIT
```sql
SELECT * FROM film
ORDER BY rental_duration
LIMIT 3;
```

# JOIN
```sql
SELECT staff.first_name, payment.*
FROM staff
JOIN payment ON staff.staff_id = payment.staff_id
```
```sql
SELECT c.first_name, c.last_name, a.address FROM customer AS c
JOIN address AS a
ON c.address_id = a.address_id
```

```sql
SELECT f.film_id, f.title, c.category_id, c.name
FROM film AS f
JOIN film_category AS fc
ON f.film_id = fc.film_id
JOIN category AS c
ON c.category_id = c.category_id

```

# USING

```sql
SELECT f.film_id, f.title, c.category_id, c.name
FROM film AS f
JOIN film_category AS fc
USING(film_id)
JOIN category AS c
USING (category_id)


```
