# Query con Group by

# 1. Contare quanti iscritti ci sono stati ogni anno

 - SELECT COUNT(`id`) AS number_of_students, YEAR(`enrolment_date`) AS `enrollment_year` FROM `students` GROUP BY YEAR(`enrolment_date`) ASC

# 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

- SELECT COUNT(`id`) AS `teachers`, `office_number` FROM `teachers` GROUP BY `office_number`

# 3.Calcolare la media dei voti di ogni appello d'esame

- SELECT `exam_id`, ROUND(AVG(`vote`), 2) FROM `exam_student` GROUP BY `exam_id`

# 4.Contare quanti corsi di laurea ci sono per ogni dipartimento

- SELECT COUNT(`id`) AS `nunber_of_courses`, `department_id` FROM `degrees` GROUP BY `department_id`


# Query con Join

# 1.Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

- SELECT `students`.* FROM `students` JOIN `degrees` ON `degrees`.id = `students`.`degree_id` WHERE `degrees`.`name` = "Corso di Laurea in Economia"
# 2.Selezionare tutti i Corsi di Laurea del Dipartimento di Neuroscienze

- SELECT `degrees`.* FROM `degrees` JOIN `departments` ON `departments`.id = `degrees`.`department_id` WHERE `departments`.`name` = "Dipartimento di Neuroscienze"

# 3.Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

- SELECT `courses`.*, `course_teacher`.teacher_id FROM `courses` JOIN `course_teacher` ON `courses`.id = `course_teacher`.course_id WHERE `course_teacher`.teacher_id = 44

# 4.Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

- 
Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami