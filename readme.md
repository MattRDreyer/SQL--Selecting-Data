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

mysql> Explain assignment;
+----------------+------------------+------+-----+---------+----------------+
| Field          | Type             | Null | Key | Default | Extra          |
+----------------+------------------+------+-----+---------+----------------+
| assignment_id  | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| student_id     | int(11) unsigned | NO   |     | NULL    |                |
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
|             4 |          4 |              1 |        1 |       17 |
|             5 |          5 |              1 |        1 |        8 |
|             6 |          6 |              1 |        1 |        4 |
|             7 |          7 |              1 |        1 |        7 |
|             8 |          8 |              1 |        1 |        3 |
|             9 |          9 |              1 |        1 |        6 |
|            10 |         10 |              1 |        1 |       15 |
|            11 |          1 |              2 |        1 |       11 |
|            12 |          2 |              2 |        1 |       16 |
|            13 |          3 |              2 |        1 |       20 |
|            14 |          4 |              2 |        1 |       19 |
|            15 |          5 |              2 |        1 |       12 |
|            16 |          6 |              2 |        1 |        9 |
|            17 |          7 |              2 |        1 |       13 |
|            18 |          8 |              2 |        1 |       10 |
|            19 |          9 |              2 |        1 |       14 |
|            20 |         10 |              2 |        1 |       18 |
+---------------+------------+----------------+----------+----------+
20 rows in set (0.00 sec)

mysql> Explain grade;
+---------------+------------------+------+-----+---------+----------------+
| Field         | Type             | Null | Key | Default | Extra          |
+---------------+------------------+------+-----+---------+----------------+
| grade_id      | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| grade_values  | varchar(30)      | YES  |     | NULL    |                |
| student_id    | int(11) unsigned | NO   |     | NULL    |                |
| assignment_id | int(11) unsigned | NO   | MUL | NULL    |                |
+---------------+------------------+------+-----+---------+----------------+
4 rows in set (0.01 sec)

mysql> select * from grade;
+----------+-----------------------------+------------+---------------+
| grade_id | grade_values                | student_id | assignment_id |
+----------+-----------------------------+------------+---------------+
|        1 | Complete and unsatisfactory |          1 |             1 |
|        2 | Exceeds Expectations        |          2 |             2 |
|        3 | Exceeds Expectations        |          8 |             8 |
|        4 | Not graded                  |          6 |             6 |
|        5 | Complete and Satisfactory   |          3 |             3 |
|        6 | Complete and Satisfactory   |          9 |             9 |
|        7 | Complete and unsatisfactory |          7 |             7 |
|        8 | Complete and Satisfactory   |          5 |             5 |
|        9 | Incomplete                  |          6 |            16 |
|       10 | Complete and Satisfactory   |          8 |            18 |
|       11 | Complete and unsatisfactory |          1 |            11 |
|       12 | Complete and Satisfactory   |          5 |            15 |
|       13 | Complete and Satisfactory   |          7 |            17 |
|       14 | Complete and Satisfactory   |          9 |            19 |
|       15 | Complete and unsatisfactory |         10 |            10 |
|       16 | Complete and Satisfactory   |          2 |            12 |
|       17 | Exceeds Expectations        |          4 |             4 |
|       18 | Complete and Satisfactory   |         10 |            20 |
|       19 | Incomplete                  |          4 |            14 |
|       20 | Exceeds Expectations        |          3 |            13 |
+----------+-----------------------------+------------+---------------+
20 rows in set (0.00 sec)
