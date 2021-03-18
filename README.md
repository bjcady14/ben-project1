# Project 1: School Administrator Application with Spring Boot

### Project Description
This application provides features for an individual in the role of a school administrator. There are two different objects the user is able to manipulate: students and courses.

### Technologies Used
* Apache-Maven 3.6.3
* Spring Tool Suite
* Docker v0.9.1-beta3
* Kubernetes

### Features

The features involving students include:

GET /students -finds all the students in the roster.
GET /students/{n} -finds information on a particular student. The student's name, n, is entered in the URI.
POST /students -adds a student to the roster: the user enters JSON in the request body of the format {"name":"John Johnson", 
email:"jjohnson@mail.com", "gpa": 3.5}
DELETE: /students/{n} -removes a student from the roster based on the name, n, given in the URI.
PUT: /students/status -updates the academic status of all students in the roster. All students have a field indicating whether or not they are on academic probation, which is initially set to 'false' for everyone in the roster. This request changes this status to 'true' for all students with a gpa less than 2.0.
GET: /students/gpa/{category} -this finds the average gpa of students based on the category given in the URI. The category is either 'all' or 'some'. /students/gpa/all calculates the average gpa of all students in the roster, while /students/gpa/some calculates the gpa of the students who are not on academic probation.
DELETE: /truncate -removes all students from the roster

The features involving the courses include:
GET /courses -finds all the courses in the course catalog.
POST /courses - adds a course to the course catalog. The user enters data as a JSON in the request body, in the format {"name":"Calculus", "professor": "Gauss", "building: "Olin"}.
DELETE /courses/{name} -removes a course by the name given in the URI.
GET /courses/Building/{building} -finds all the courses in the building given in the URI.