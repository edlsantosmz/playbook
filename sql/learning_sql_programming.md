## Ask data from two or more tables
### Join types
#### Cross Join
`SELECT * FROM people JOIN states;`
![alt text](https://github.com/edlsantosmz/playbook/blob/master/sql/sql_ch2_img1_join.png)

#### Inner Join
Ask for records that overlap

`SELECT * FROM <right_table> JOIN <left_table> ON <right_table>.column = <left_table>.column;`
`SELECT * FROM people JOIN states ON people.state = states.abbr;`

![alt text](https://github.com/edlsantosmz/playbook/blob/master/sql/sql_ch2_img2_inner_join.png)

#### LEFT (Outer) Join
`SELECT * FROM poeple LEFT JOIN states ON people.state = people.abbr;`
![alt text](https://github.com/edlsantosmz/playbook/blob/master/sql/sql_ch2_img3_left_join.png)

#### RIGHT (Outer) Join
`SELECT * FROM people RIGHT JOIN states ON people.state = states.abbr;`

* * Not supported by SQLite

![](https://github.com/edlsantosmz/playbook/blob/master/sql/sql_ch2_img4_right_join.png)

#### FULL (Outer) JOIN
`SELECT * FROM people FULL OUTER JOIN states ON people.states = states.abbr;`

* Not supported by MySQL, SQLite

![](https://github.com/edlsantosmz/playbook/blob/master/sql/sql_ch2_img5_full_outer_join.png)

#### Examples
```
SELECT DISTINCT(people.state), states.state_abbr
FROM state
LEFT JOIN people ON people.state = states.state_abbr
ORDER BY people.state;
```

### Combine results
Let's count out the number of people that got 10, 20, 30, 40 and so on points.

```
SELECT state, quiz_points, COUNT(quiz_points)
FROM people
GROUP BY state, quiz_points;
```
## Data types, math and helpful functions
### Data types in SQL
http://www-db.deis.unibo.it/courses/TW/DOCS/w3schools/sql/sql_datatypes_general.asp.html

### MATH
```
SELECT 2*(5+1);
12
```
### Subqueries
In order to get a list of participants who earned the maximum score on our quiz, we might write a query that looks like this:
`SELECT first_name, last_name, quiz_points FROM people WHERE quiz_points=(SELECT MAX(quiz_points) FROM people);`

### Transform data
This statement will replace the letter "d" in students' first names with an underscore:
`SELECT REPLACE(first_name, 'd', '-') FROM Student;`

* `CAST(<field> AS <TYPE>)`
* `CAST(age AS CHAR)`
* `SELECT MAX( CAST( quiz_points AS INT ) from people;`

### Use aliases to shorten field names
The AS keyword lets you change field names into more descriptive or concise names.
```
SELECT first_name, last_name AS surname
FROM people;
```

## Add or Modify Data
### Add data to a table
```
INSERT INTO tablename (field1, field2)
VALUES (value1, value2);

INSERT INTO people (first_name, last_name, state)
VALUES ('Mary', 'Hamilton', 'OR');

INSERT INTO people (first_name, last_name)
VALUES ('George', 'White'), ('Jen', 'Smith'), ('Carol', 'Andersson');
```

### Modify data on a table
```
UPDATE 
  tablename
SET
  field1 = value1,
  field2 = value2
WHERE
  condition;
  
UPDATE
  people
SET
  first_name = 'Martha'
WHERE
  first_name = 'George' AND last_name = 'White';
```

Write a statement to update the middle name of the customer if that value was not provided.
`UPDATE Customer SET MiddleName = 'NONE' WHERE MiddleName IS NULL;`
NULL is not a numeric value, so we need to test whether the value IS NULL or IS NOT NULL rather than treating it like zero.

### Remove data from a table
```
DELETE FROM tablename
WHERE condition;

DELETE FROM people
WHERE id_number IS NULL;

```

## OVERCOMING COOMON MISTAKES
* Typos and syntax erros - read the error, break down statement.
* Put text values in 'single quotes'
* Put field names with spaces ``inside backticks``, not best practices.
* Keep development journal in `plain text`
* Copy/paste to/form plain text rather than formatted text
* Smart quotes `(´ ´ vs ' ' )` can cause problems
* Share statements as plain-text.sql attachments rather than in chat/email
* To find `null` values, use `IS NULL` or `IS NOT NULL` instead of ``0``, ``no``or ``false`` 
* You should tes your matching conditions before using them for a destructive action `(UPDATE/DELETE)`

## Follow-up courses
### More Advanced SQL
* SQL Essential Training
* SQL: Data Reporting and Analysis
* SQL Tips, Tricks, & Techniques

### Build an Application with a Database
* PHP with MySQL Essential Training
* Java: Database Access with Hibernate





