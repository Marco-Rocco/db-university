n 1

SELECT 
    `id`, `name`, `surname`, `date_of_birth`
FROM
    `db-university`.students
WHERE YEAR 
	(`date_of_birth`)= 1990;
	
