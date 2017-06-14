```sql

ITEM 1.
SELECT first_name, last_name
FROM student

first_name	last_name
Eric	Ephram
Greg	Gould
Adam	Ant
Howard	Hess
Charles	Caldwell
James	Joyce
Doug	Dumas
Kevin	Kraft
Frank	Fountain
Brian	Biggs

ITEM 2.
SELECT *
FROM student
WHERE years_of_experience < 8

student_id	first_name	last_name	years_of_experience	start_date
1	Eric	Ephram	2	2016-03-31
2	Greg	Gould	6	2016-09-30
3	Adam	Ant	5	2016-06-02
4	Howard	Hess	1	2016-02-28
5	Charles	Caldwell	7	2016-05-07
8	Kevin	Kraft	3	2016-04-15
10	Brian	Biggs	4	2015-12-25

ITEM 3.
SELECT last_name, start_date, student_id
FROM student
Order By last_name;

last_name	start_date	student_id
Ant	2016-06-02	3
Biggs	2015-12-25	10
Caldwell	2016-05-07	5
Dumas	2016-07-04	7
Ephram	2016-03-31	1
Fountain	2016-01-31	9
Gould	2016-09-30	2
Hess	2016-02-28	4
Joyce	2016-08-27	6
Kraft	2016-04-15	8

ITEM 4.
SELECT *
FROM student
WHERE first_name IN ('Adam', 'James', 'Frank')
Order By last_name DESC;

student_id	first_name	last_name	years_of_experience	start_date
6	James	Joyce	9	2016-08-27
9	Frank	Fountain	8	2016-01-31
3	Adam	Ant	5	2016-06-02

ITEM 5.
SELECT first_name, last_name, start_date
FROM student
WHERE start_date BETWEEN '2016-01-01' AND '2016-06-30'
Order By start_date DESC

first_name	last_name	start_date
Adam	Ant	2016-06-02
Charles	Caldwell	2016-05-07
Kevin	Kraft	2016-04-15
Eric	Ephram	2016-03-31
Howard	Hess	2016-02-28
Frank	Fountain	2016-01-31

mysql> explain assignment;
+----------------+------------------+------+-----+---------+----------------+
| Field          | Type             | Null | Key | Default | Extra          |
+----------------+------------------+------+-----+---------+----------------+
| assignment_id  | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| student_id     | int(11) unsigned | NO   | MUL | NULL    |                |
| assignment_nbr | int(11)          | NO   |     | NULL    |                |
| class_id       | int(11) unsigned | NO   |     | NULL    |                |
| grade_id       | int(11) unsigned | YES  | MUL | NULL    |                |
+----------------+------------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

mysql> select * from assignment;
+---------------+------------+----------------+----------+----------+
| assignment_id | student_id | assignment_nbr | class_id | grade_id |
+---------------+------------+----------------+----------+----------+
|             1 |          1 |              1 |        1 |        1 |
|             2 |          2 |              1 |        1 |        2 |
|             3 |          3 |              1 |        1 |        5 |
|             4 |          4 |              1 |        1 |        3 |
|             5 |          5 |              1 |        1 |        4 |
+---------------+------------+----------------+----------+----------+
5 rows in set (0.00 sec)

mysql> explain grade;
+--------------+------------------+------+-----+---------+----------------+
| Field        | Type             | Null | Key | Default | Extra          |
+--------------+------------------+------+-----+---------+----------------+
| grade_id     | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| grade_values | varchar(30)      | YES  |     | NULL    |                |
+--------------+------------------+------+-----+---------+----------------+
2 rows in set (0.01 sec)

mysql> select * from grade;
+----------+-----------------------------+
| grade_id | grade_values                |
+----------+-----------------------------+
|        1 | Complete and unsatisfactory |
|        2 | Exceeds Expectations        |
|        3 | Complete and Satisfactory   |
|        4 | Not graded                  |
|        5 | Incomplete                  |
+----------+-----------------------------+
5 rows in set (0.00 sec)

'''
