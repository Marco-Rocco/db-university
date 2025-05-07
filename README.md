DAY 2

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



N8

SELECT 
    *
FROM
    `db-university`.teachers
WHERE
`phone` IS NULL;





DAY 3


N1


SELECT 
  COUNT(*), YEAR(`enrolment_date`) AS `enrolling_year`
FROM
    `students`
GROUP BY `enrolling_year`
ORDER BY `enrolling_year`;


N2

SELECT
	COUNT(*), `office_address`
FROM
	`teachers`
GROUP BY
	`office_address`;


N3

SELECT
	AVG(`vote`) AS `average_vote`
FROM
	`exam_student`
GROUP BY
	`vote`
ORDER BY 
	`vote`;


N4

SELECT 
	COUNT(`name`)
FROM
    `degrees`
GROUP BY `department_id`;


N1 JOIN


SELECT 
    `students`.*,  `degrees`.`name`
FROM
    `students`
        INNER JOIN
    `degrees` ON `degrees`.`id` = `students`.`degree_id`
WHERE
    `degrees`.`name` LIKE '%economia%'