```
-- Find the names of all the instructors from Biology department
SELECT name
FROM instructor
WHERE dept_name = "Biology";

-- Find the names of courses in Computer science department which have 3 credits
SELECT title
FROM course
WHERE credits = 3 
AND dept_name = "Comp. Sci.";

-- join the "teaches" and "instructor" relation on the "ID" attribute. Output all attributes
SELECT *
FROM teaches
INNER JOIN instructor
ON teaches.ID = instructor.ID;

-- List the names of all of the professors teaching in Spring 2018 sorted in alphabetical order (no duplicates)

SELECT DISTINCT name
FROM teaches
INNER JOIN instructor
ON teaches.ID = instructor.ID
WHERE semester = "Spring"
AND year = 2018
ORDER BY name;

-- Output the course id and title of every course that serves a prereq. Your output should not include any duplicates.

SELECT DISTINCT course.course_id, course.title
FROM prereq
INNER JOIN course
ON prereq.prereq_id = course.course_id;

-- Output a relation with two attributes, "student_name" and "advisor_name", which matches the name of the student to the name of their advisor.


SELECT student.name AS student_name, instructor.name AS advisor_name
FROM advisor
INNER JOIN student
ON advisor.s_ID = student.ID
INNER JOIN instructor
ON advisor.i_ID = instructor.ID;

-- For the student with ID 45678, show all course_id and title of all courses registered for by the student in Spring 2018.

SELECT course.course_id, title
FROM student
INNER JOIN takes
ON student.ID = takes.ID
INNER JOIN course 
ON takes.course_id = course.course_id
WHERE student.ID = 45678
AND semester = "Spring" 
AND year = 2018;




-- Use SQL aggregation to find the total number of credits the student with ID 45678 is taking in Spring 2018

-- Use SQL aggregation to find the total number of credits taken by each student in Spring 2018. Omit any students who are not registered for any classes in Spring 2018.

-- Find the names of all students who have taken any Comp. Sci. course ever (there should be no duplicate names)

-- Display the IDs of all instructors who have never taught a course. 

-- Display the names and IDs of all instructors who have never taught a course. 

```
