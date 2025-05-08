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

N2 JOIN 


SELECT 
    `degrees`.name,  `degrees`.`level`, `departments`.`name` AS `department_name`
FROM
    `degrees`
        INNER JOIN
    `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE
    `departments`.`name` = 'Dipartimento di Neuroscienze'
        AND `degrees`.`level` = 'Magistrale';


N3 JOIN 

SELECT 
    `teachers`.`surname`, `course_teacher`.`course_id`
FROM
    `teachers`
        INNER JOIN
    `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id`
        INNER JOIN
    `courses` ON `course_teacher`.`course_id` = `courses`.`id`
WHERE
    `teachers`.`id` = 44



N4 JOIN

SELECT 
    *
FROM
    `students`
    INNER JOIN 
    `degrees` ON `students`.`degree_id` = `degrees`.`id`
    INNER JOIN
    `departments` ON `degrees`.`department_id` = `departments`.`id`
    ORDER BY `students`.`surname`, `students`.`name`


N5 JOIN


SELECT 
    `degrees`.name, `degrees`.level, `courses`.name, `teachers`.name
FROM
    `degrees`
    INNER JOIN  `courses` ON `courses`.`degree_id` = `degrees`.id
    INNER JOIN `teachers` ON `courses`.`degree_id` = `teachers`.id;