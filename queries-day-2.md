# Query con Group by

# 1. Contare quanti iscritti ci sono stati ogni anno

 - SELECT COUNT(`id`) AS number_of_students, YEAR(`enrolment_date`) AS `enrollment_year` FROM `students` GROUP BY YEAR(`enrolment_date`) ASC

# 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

- SELECT COUNT(`id`) AS `teachers`, `office_number` FROM `teachers` GROUP BY `office_number`

# 3.Calcolare la media dei voti di ogni appello d'esame

- SELECT `exam_id`, ROUND(AVG(`vote`), 2) FROM `exam_student` GROUP BY `exam_id`

# 4.Contare quanti corsi di laurea ci sono per ogni dipartimento

- SELECT COUNT(`id`) AS `nunber_of_courses`, `department_id` FROM `degrees` GROUP BY `department_id`

