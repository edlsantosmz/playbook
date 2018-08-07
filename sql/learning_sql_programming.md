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

![](https://github.com/edlsantosmz/playbook/blob/master/sql/sql_ch2_img4_right_join.png)

#### FULL (Outer) JOIN
`SELECT * FROM people FULL OUTER JOIN states ON people.states = states.abbr;`

![](https://github.com/edlsantosmz/playbook/blob/master/sql/sql_ch2_img5_full_outer_join.png)

