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
