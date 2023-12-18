`Manipulation - codecademy`

```html
<!--Introduction to SQL-->
SELECT * FROM celebs;

<!--Relational Databases-->
<!--INTEGER, a positive or negative whole number-->
<!--TEXT, a text string-->
<!--DATE, the date formatted as YYYY-MM-DD-->
<!--REAL, a decimal value-->

<!--Statements-->
CREATE TABLE table_name (
   column_1 data_type, 
   column_2 data_type, 
   column_3 data_type
);


<!--Create(not yet available)-->
CREATE TABLE celebs (
   id INTEGER, 
   name TEXT, 
   age INTEGER
);

<!--Insert(not yet available)-->
<!--The INSERT statement inserts a new row into a table-->
<!--This database schema has 4 rows of data-->

INSERT INTO celebs (id, name, age) 
VALUES (1, 'Justin Bieber', 22);

INSERT INTO celebs (id, name, age) 
VALUES (2, 'Beyonce Knowles', 33); 

INSERT INTO celebs (id, name, age) 
VALUES (3, 'Jeremy Lin', 26); 

INSERT INTO celebs (id, name, age) 
VALUES (4, 'Taylor Swift', 26); 

<!--Select(not yet available)-->
<!--SELECT statements are used to fetch data from a database-->
SELECT name FROM celebs;
SELECT * FROM celebs;

<!--Alter(not yet available)-->
<!--ALTER TABLE is a clause that lets you make the specified changes-->
ALTER TABLE celebs 
ADD COLUMN twitter_handle TEXT;

<!--Update(not yet available)-->
<!--UPDATE(table) SET(column) WHERE(row) edits a row in a table-->
UPDATE celebs 
SET twitter_handle = '@taylorswift13' 
WHERE id = 4; 

<!--Delete(not yet available)-->
ELETE FROM celebs 
WHERE twitter_handle IS NULL;

<!--Constraints-->


```

`Queries - codecademy`

```html

```

`Aggregate Functions - codecademy`

```html

```

`Multiple Tables - codecademy`

```html

```


`The INSERT Statement`

```html
INSERT INTO actor (id, first_name, last_name)
     VALUES (201, 'Troy', 'McClure');

INSERT INTO film_actor (actor_id, film_id)
     VALUES (201, 1);

SELECT actor.first_name, actor.last_name, film.title, film.description
FROM actor
JOIN film_actor ON actor.id = film_actor.actor_id
JOIN film ON film_actor.film_id = film.id
WHERE actor.id = 201;
```

`The UPDATE Statement`

```html
UPDATE film
   SET rental_duration = 7,
       rental_rate = 1.99
 WHERE id = 993;

UPDATE film
SET replacement_cost = 22.99
WHERE id = 1;
```

`The DELETE Statement`

```html
DELETE FROM payment
WHERE id >= 56273;

SELECT * FROM payment WHERE id >=56000;
```

``

```html
START TRANSACTION

UPDATE address SET street = "3.14159 PIE Lane"
WHERE id = 1;

COMMIT
```

`Labs`

```html
START TRANSACTION
INSERT INTO actor (first_name, last_name) 
VALUES ('Deonna', 'Aponte');
COMMIT

START TRANSACTION
INSERT INTO film_actor (actor_id, film_id) 
VALUES (202, 100);
COMMIT

START TRANSACTION
INSERT INTO address (address, city, state_province, phone) 
VALUES (123 Main St, Los Angeles, CA, 1231231234);
SELECT LAST_INSERT_ID();
COMMIT

START TRANSACTION
INSERT INTO staff (first_name, last_name, address_id, store_id, ...) 
VALUES ('YourFirstName', 'YourLastName', 303, YourStoreID, ...);
SELECT LAST_INSERT_ID();
COMMIT
```

``

```html

```

``

```html

```

``

```html

```

``

```html

```

``

```html

```