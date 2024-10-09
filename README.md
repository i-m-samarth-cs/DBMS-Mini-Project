# student-management-system
Student management system project in python

****Requirements and Installation****

Use pip3 instead of pip for Linux and Mac.

Install PyMySQL
☛pip install PyMySQL

Install Tkinter
☛pip install tk



****Install MySQL server****



****Create a Database and a Table****

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sakila             |
| sys                |
| world              |
+--------------------+
6 rows in set (0.11 sec)

mysql> CREATE DATABASE student_management;
Query OK, 1 row affected (0.05 sec)

mysql> create table student_register(
    ->  f_name VARCHAR(50) NOT NULL,
    ->  l_name VARCHAR(50) NOT NULL,
    ->  course VARCHAR(30) NOT NULL,
    ->  subject VARCHAR(50) NOT NULL,
    ->  year Int(10) NOT NULL,
    ->  age Int(10) NOT NULL,
    ->  gender char(10) NOT NULL,
    ->  birth DATE NOT NULL,
    ->  contact VARCHAR(15) NOT NULL,
    ->  email VARCHAR(100) NOT NULL,
    ->  PRIMARY KEY ( contact )
    -> );
ERROR 1046 (3D000): No database selected
mysql> use database student_management;
ERROR 1049 (42000): Unknown database 'database'
mysql> use student_management;
Database changed
mysql> create table student_register(
    ->  f_name VARCHAR(50) NOT NULL,
    ->  l_name VARCHAR(50) NOT NULL,
    ->  course VARCHAR(30) NOT NULL,
    ->  subject VARCHAR(50) NOT NULL,
    ->  year Int(10) NOT NULL,
    ->  age Int(10) NOT NULL,
    ->  gender char(10) NOT NULL,
    ->  birth DATE NOT NULL,
    ->  contact VARCHAR(15) NOT NULL,
    ->  email VARCHAR(100) NOT NULL,
    ->  PRIMARY KEY ( contact )
    -> );
Query OK, 0 rows affected, 2 warnings (0.12 sec)

mysql> select * from student_register;
Empty set (0.08 sec)

mysql> DESC student_register;
+---------+--------------+------+-----+---------+-------+
| Field   | Type         | Null | Key | Default | Extra |
+---------+--------------+------+-----+---------+-------+
| f_name  | varchar(50)  | NO   |     | NULL    |       |
| l_name  | varchar(50)  | NO   |     | NULL    |       |
| course  | varchar(30)  | NO   |     | NULL    |       |
| subject | varchar(50)  | NO   |     | NULL    |       |
| year    | int          | NO   |     | NULL    |       |
| age     | int          | NO   |     | NULL    |       |
| gender  | char(10)     | NO   |     | NULL    |       |
| birth   | date         | NO   |     | NULL    |       |
| contact | varchar(15)  | NO   | PRI | NULL    |       |
| email   | varchar(100) | NO   |     | NULL    |       |
+---------+--------------+------+-----+---------+-------+
10 rows in set (0.09 sec)


mysql -u root -p
Replace root with your MySQL username if it’s different, and you’ll be prompted for the MySQL root password.


2. Create a New User:
To create a new MySQL user, you can use the `CREATE USER` command. Replace `username` and `password` with your desired username and password:

CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
This creates a user called `username` that can only connect from the local machine. If you want to allow connections from any host, replace `localhost` with `%`.

3. Grant Privileges:
You can use the `GRANT` statement to assign privileges to the user. Here’s how to grant various privileges:

Grant all privileges on a specific database:
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
Grant specific privileges (e.g., GRANT CREATE, ALTER, DROP, INSERT, UPDATE, INDEX, DELETE, SELECT, REFERENCES, RELOAD) on a specific database:
GRANT SELECT, INSERT, UPDATE, DELETE ON database_name.* TO 'username'@'localhost';
Replace `database_name` with the name of the database you want to grant access to.

Grant all privileges on all databases (not recommended for security reasons):
GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost';
4. Apply Privileges:
After granting privileges, you need to apply the changes using the FLUSH PRIVILEGES command:

FLUSH PRIVILEGES;
5. Exit MySQL:
Now you can exit the MySQL Client:

exit;
