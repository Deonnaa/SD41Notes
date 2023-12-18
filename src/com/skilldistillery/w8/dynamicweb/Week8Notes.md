## [Week 8](https://github.com/SkillDistillery/SD41/blob/main/sql2/README.md)

### MySQL WorkBench

#### MySQL Workbench
#### Configure MySQL WorkBench
#### Using the SQL WorkBench editor

### Data Manipulation and Transactions

#### The INSERT Statement
#### The UPDATE Statement
#### The DELETE Statement
#### Transaction Management
#### Concurrency and Locking
#### Loading Data from External Sources
#### Lab

`INSERT Notes`

```html
<!--Add Actor to table-->
INSERT INTO actor (id, first_name, last_name)
     VALUES (201, 'Troy', 'McClure');
     
SELECT * FROM actor WHERE id = 201;

<!--Add new Actor to movie-->
INSERT INTO film_actor (actor_id, film_id)
     VALUES (201, 1);                     -- Add Troy to ACADEMY DINOSAUR

<!--Shows all films with actor 201-->
SELECT actor.first_name, actor.last_name, film.title, film.description
FROM film 
JOIN film_actor ON film.id = film_actor.film_id
JOIN actor ON actor.id = film_actor.actor_id
WHERE actor.id = 201;

<!--JUST BECAUSE YOU CAN DOESN'T MEAN YOU SHOULD-->
INSERT INTO actor VALUES (607,'Weirdo', 'Jones');

<!--Yes, do not make fields the database can do for you-->
INSERT INTO actor VALUES (first_name, last_name) 
VALUES('Troyette','McClurette');

<!--Added film id's of Actor 201 with 'LOSE' in title-->
INSERT INTO film_actor (actor_id, film_id)
     SELECT 201, id FROM film WHERE title LIKE '%LOSE%';

<!--Actor now has new movies with the 'LOSE' in title-->
<!--Shows all films with actor 201-->
SELECT actor.first_name, actor.last_name, film.title, film.description
FROM film 
JOIN film_actor ON film.id = film_actor.film_id
JOIN actor ON actor.id = film_actor.actor_id
WHERE actor.id = 201;

<!--mySQL specific function-->
SELECT LAST_INSERT_ID();

<!--SUBQUERY mySQL specific function-->
SELECT * FROM address WHERE id = (SELECT last_insert_id());

<!--JUST BECAUSE YOU CAN DOESN'T MEAN YOU SHOULD-->
INSERT INTO address
     VALUES (730, '123 Fake St.', NULL, 'Roswell', 'New Mexico', NULL, NULL, '5551234');
```

`UPDATE Notes`

```html
<!--NEVER FORGET WHERE because it will update entire database-->
UPDATE film
SET rental_duration = 7, rental_rate = 1.99
WHERE id = 993;
 
UPDATE film
SET replacement_cost = 22.99 
WHERE id = 1;

<!--Database can do the math for you!-->
UPDATE film
SET replacement_cost = replacement_cost + 1.39
WHERE id = 1;

<!--Change supervisor id to the one of store 4 (Staff id 71, supr_id was 62 > 1)-->
UPDATE staff
SET supervisor_id = (SELECT manager_id
                     FROM store
                     WHERE id = 4)
WHERE id = 71;

<!--Specify DEFAULT to set a value back to the default value specified for this column when the table was created-->  
<!--NEVER FORGET WHERE because it will update entire database-->
UPDATE film
SET rating = DEFAULT
WHERE id = 132;
```

`DELETE Notes`

```html
<!--NEVER FORGET WHERE because it will update entire database-->
DELETE FROM payment
WHERE id >= 56000;

SELECT * FROM payment WHERE id >= 56000;
```

`Transaction Management Notes`

```html
<!--START TRANSACTION;-->
<!--ROLLBACK;-->
<!--COMMIT;-->

START TRANSACTION;

INSERT INTO address( address, city, state_province, country_code, phone)
     VALUES ('123 Fake St', 'Denver', 'CO', 'US', '5551234');
INSERT INTO staff ( first_name, last_name, address_id, store_id, active, username)
     VALUES ( 'Bob', 'Dobbs', LAST_INSERT_ID(), 2, 1, 'bdobbs');
UPDATE staff SET supervisor_id = (SELECT manager_id FROM store
                                   WHERE store.id = staff.store_id)
WHERE id = LAST_INSERT_ID();

<!--If you forget to commit the computer will auto 'ROLLBACK' for you-->
COMMIT;

<!--Use 'LIKE' if using '%'-->
SELECT * FROM address WHERE street LIKE %PI%;
```

`Labs`

```html
START TRANSACTION;
INSERT INTO actor (first_name, last_name) 
VALUES ('Deonna', 'Aponte')
COMMIT;

START TRANSACTION;
INSERT INTO film_actor (actor_id, film_id) 
VALUES (202, 100)
COMMIT;

START TRANSACTION;
INSERT INTO address (address, city, state_province, phone) 
VALUES (123 Main St, Los Angeles, CA, 1231231234);
SELECT LAST_INSERT_ID()
COMMIT;

START TRANSACTION;
INSERT INTO staff (first_name, last_name, address_id, store_id, ...) 
VALUES ('YourFirstName', 'YourLastName', 303, YourStoreID, ...);
SELECT LAST_INSERT_ID()
COMMIT;






```

### JDBC SQL Programming

#### Executing Ad Hoc SQL
#### ResultSetMetaData
#### Executing SQL Updates
#### Retrieving Generated Keys
#### Transaction Management
#### Error Handling and SQLException
#### Lab


### ORM - Object-Relational Mapping

#### Creating Database Entities from Java Objects
#### Updates
#### Deletes
#### Lab - ORM for DML

``

```html

```

### Outer, Self, and Other Joins

#### Outer Joins
#### Self Joins
#### Equijoins, Non-Equijoins, and Antijoins
#### Lab

``

```html

```

### Subqueries and Aggregate Functions

#### Subqueries
#### Correlated Subqueries
#### The EXISTS Operator
#### Aggregate Functions
#### GROUP BY
#### Lab

``

```html

```

### Modeling and MySQL WorkBench

#### Data Modeling - Reverse Engineer
#### Data Modeling
#### Data Modeling - Forward Engineer
#### Model Data Inserts

``

```html

```