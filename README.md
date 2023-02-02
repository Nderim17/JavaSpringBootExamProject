# JavaSpringBootExamProject

University Management System

#Clone from git:
https://github.com/Nderim17/JavaSpringBootExamProject

#How to run this project:
Import Database menagement.sql
open folder JavaSpringBootExamProject
Go to src/main/java/com.example.javaspringbootexamproject/javaspringbootexamprojjectapplication
Run

#Endpoint - Example

#DDL
CREATE TABLE `course` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
)

CREATE TABLE `faculty` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  `university_id` int NOT NULL,
  PRIMARY KEY (`id`)
) 

CREATE TABLE `student` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  `faculty_id` int DEFAULT NULL,
  `university_id` int DEFAULT NULL,
  PRIMARY KEY (`id`)
) 

CREATE TABLE `student_course` (
  `student_id` int NOT NULL,
  `course_id` int NOT NULL
) 

CREATE TABLE `university` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) 


1.URL: http://localhost:8081/university/all GET All Universities 
Method : GET

Response:
[
    {
        "id": 1,
        "name": "FON"
    },
    {
        "id": 2,
        "name": "SEEU"
    }
]

2.URL: http://localhost:8081/university/addUniversity ADD University
Method: POST

Response:
{
    "id": 3,
    "name": "USHT"
}

3. URL: http://localhost:8081/student/all GET All Students
Method: GET

Response:
[
    {
        "id": 3,
        "name": "Deniz Zaimi",
        "courses": [],
        "university": {
            "id": 2,
            "name": "SEEU"
        },
    {
        "id": 5,
        "name": "Nderim Islami",
        "courses": [],
        "university": {
            "id": 1,
            "name": "FON"
        }
        
    }
]

4.URL: http://localhost:8081/student/addStudent ADD Student
Method: POST


Response:
{
    "id": 6,
    "name": "YLL Limani",
    "courses": null,
    "university": null,
    "faculty": null
}

5.URL: http://localhost:8081/faculty/all GET All Faculties
Method: GET

Response:
[
    {
        "id": 2,
        "name": "CST"
    },
    {
        "id": 3,
        "name": "LAW"
    }
]

6.URL: http://localhost:8081/course/all GET All Courses
Method: GET

[
    {
        "id": 1,
        "name": "Database Management Systems"
    },
    {
        "id": 2,
        "name": "Programming in Java"
    }
]

7.URL: http://localhost:8081/course/addCourse Add Course
Method: POST

Response:
{
    "id": 3,
    "name": "Computer Networks"
}

8.URL : http://localhost:8081/course/course/6
Method: PUT
 {"id": 6 ,"name": "Computer Architecture"}

Response:
{
    "id": 5,
    "name": "Computer Architecture"
}

8.URL: http://localhost:8081/course/course/3
Method: Delete
[
   
    {
        "id": 3,
        "name": "Computer Networks"
    }
]

8.URL : http://localhost:8081/faculty/faculty/2
Method: Delete
 [
 
    {
        "id": 2,
        "name": "CST"
    }
 ]

9.URL: http://localhost:8081/student/student/8
Method: Delete

{
        "id": 8
        
        
        }
