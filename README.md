# alyra-exercices-database

ex01:

postgres=> CREATE DATABASE db_1;
CREATE DATABASE
postgres=> CREATE TABLE users (id SERIAL PRIMARY KEY, name VARCHAR(30), password VARCHAR(30));
CREATE TABLE
postgres=> INSERT INTO users (name, password) VALUES ('alice', '123'), ('bob', '456'), ('charlie', '789');
INSERT 0 3
postgres=> SELECT \* FROM users;
id | name | password
----+---------+----------
1 | alice | 123
2 | bob | 456
3 | charlie | 789
(3 rows)

ex02:

postgres=> INSERT INTO users (name, password) VALUES ('dan', '101112'), ('eve', '131415'), ('faythe', '161718');
INSERT 0 3
postgres=> SELECT \* FROM users;
id | name | password
----+---------+----------
1 | alice | 123
2 | bob | 456
3 | charlie | 789
4 | dan | 101112
5 | eve | 131415
6 | faythe | 161718
(6 rows)

ex03:

postgres=> SELECT \* FROM users WHERE length(password) > 3 ;
id | name | password
----+--------+----------
4 | dan | 101112
5 | eve | 131415
6 | faythe | 161718
(3 rows)

ex04:

postgres=> ALTER TABLE users ADD COLUMN bio TEXT DEFAULT 'Hello, world';
ALTER TABLE
postgres=> SELECT \* FROM users
postgres-> ;
id | name | password | bio
----+---------+----------+--------------
1 | alice | 123 | Hello, world
2 | bob | 456 | Hello, world
3 | charlie | 789 | Hello, world
4 | dan | 101112 | Hello, world
5 | eve | 131415 | Hello, world
6 | faythe | 161718 | Hello, world
(6 rows)
