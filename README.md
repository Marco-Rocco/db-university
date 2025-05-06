n 1

SELECT 
    `id`, `name`, `surname`, `date_of_birth`
FROM
    `db-university`.students
WHERE YEAR 
	(`date_of_birth`)= 1990;
	
 

n2

SELECT 
    `name`, `cfu`
FROM
    `db-university`.courses
WHERE
	`cfu` > 10;



n3

SELECT 
    *
FROM
    `db-university`.students
WHERE
	YEAR(CURDATE()) - YEAR(date_of_birth) > 30;
    
    
n4

SELECT 
    *
FROM
    `db-university`.courses
WHERE
	`year` = 1
AND
	`period` = 'I semestre'


n5

SELECT 
    *
FROM
    `db-university`.exams
WHERE
	`date` = '2020-06-20'
AND
	`hour` > '14:00:00';


n6

SELECT 
    *
FROM
    `db-university`.degrees
WHERE
	`level` = 'magistrale';

    


n7

SELECT 
    `id`
FROM
    `db-university`.departments;