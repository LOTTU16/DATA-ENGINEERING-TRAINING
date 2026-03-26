CREATE DATABASE capstone_sql;
USE capstone_sql;
CREATE TABLE students (
student_id INT PRIMARY KEY,
student_name VARCHAR(100),
city VARCHAR(50),
age INT
);
CREATE TABLE enrollments (
enrollment_id INT PRIMARY KEY,
student_id INT,
course_name VARCHAR(100),
trainer VARCHAR(100),
fee DECIMAL(10,2)
);
INSERT INTO students VALUES
(1,'Aarav Sharma','Hyderabad',22),
(2,'Priya Reddy','Bangalore',23),
(3,'Rahul Verma','Mumbai',24),
(4,'Sneha Kapoor',NULL,21),
(5,'Vikram Singh','Chennai',25),
(6,NULL,'Delhi',22);
INSERT INTO enrollments VALUES
(101,1,'MySQL','Abdullah Khan',5000),
(102,1,'Python','Abdullah Khan',7000),
(103,2,'Power BI','Kiran',6000),
(104,3,'Azure Data Factory','Sneha',8000),
(105,NULL,'Excel','Rohan',3000),
(106,8,'Databricks','Ananya',9000);
SELECT Students.student_name,
enrollments.course_name
FROM Students
INNER JOIN enrollments ON 
Students.student_id=enrollments.student_id;
SELECT Students.student_name,
enrollments.course_name
FROM Students
LEFT JOIN enrollments ON
Students.student_id=
enrollments.student_id;
SELECT Students.student_name,
enrollments.course_name
FROM Students
RIGHT JOIN enrollments ON
Students.student_id=
enrollments.student_id;
SELECT Students.student_name,
enrollments.course_name
FROM Students
LEFT JOIN enrollments ON
Students.student_id=
enrollments.student_id
UNION
SELECT Students.student_name,
enrollments.course_name
FROM Students
RIGHT JOIN enrollments ON
Students.student_id=
enrollments.student_id;
SELECT Students.student_name,
enrollments.course_name
FROM Students
CROSS JOIN enrollments;
SELECT Students.student_name, enrollments.course_name
FROM Students
INNER JOIN enrollments ON Students.student_id = enrollments.student_id
WHERE Students.city = 'Hyderabad';
SELECT course_name, fee 
FROM enrollments 
WHERE fee > 6000;
SELECT Students.student_name, COUNT(enrollments.course_name) AS total_courses
FROM Students
INNER JOIN enrollments ON Students.student_id = enrollments.student_id
GROUP BY Students.student_name;
SELECT Students.student_name, SUM(enrollments.fee) AS total_fee_paid
FROM Students
INNER JOIN enrollments ON Students.student_id = enrollments.student_id
GROUP BY Students.student_name;
SELECT Students.student_name, COUNT(enrollments.course_name) AS course_count
FROM Students
INNER JOIN enrollments ON Students.student_id = enrollments.student_id
GROUP BY Students.student_name
HAVING COUNT(enrollments.course_name) > 1;
SELECT trainer, SUM(fee) AS total_collected
FROM enrollments
GROUP BY trainer
HAVING SUM(fee) > 10000;
SELECT city, COUNT(student_id) AS student_count
FROM Students
GROUP BY city
HAVING COUNT(student_id) > 1;
SELECT Students.student_name, 
       Students.city, 
       SUM(enrollments.fee) AS total_fee_paid
FROM Students
INNER JOIN enrollments ON Students.student_id = enrollments.student_id
GROUP BY Students.student_name, Students.city
HAVING SUM(enrollments.fee) > 5000
ORDER BY total_fee_paid DESC;
