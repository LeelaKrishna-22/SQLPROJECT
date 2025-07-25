📘 Student Grading and GPA Management System: This project is a SQLite-based academic records management system for handling student grades, calculating GPA, and summarizing semester results. It includes tables for students, courses, semesters, grades, and GPA. The system also integrates triggers and views for automation and reporting.

Tables Creation:
Creates 5 main tables — Students, Courses, Semesters, Grades, and GPA — to store student details, subjects, exam records, and GPA.

Data Insertion:
Inserts sample data for students, courses, semesters, and their grades (marks + letter grades).

GPA Table:
A separate table GPA stores each student's semester-wise GPA, calculated using grade points (A=10, B=8, etc.).

Trigger for GPA Calculation:
A trigger trg_gpa_calc automatically updates the GPA table whenever a new grade is added.

Semester Result View:
A view SemesterResultSummary shows each student’s name, semester, course, and grade for easy reporting.

Drop Statements:
Existing tables are dropped first to allow smooth re-creation without errors.

1. Drop Existing Tables

DROP TABLE IF EXISTS GPA;
DROP TABLE IF EXISTS Grades;
DROP TABLE IF EXISTS Semesters;
DROP TABLE IF EXISTS Courses;
DROP TABLE IF EXISTS Students;

 2. Create Students Table

CREATE TABLE Students (
    student_id INTEGER PRIMARY KEY,
    name TEXT,
    dept TEXT,
    batch_year INTEGER
);

 3. Create Courses Table

CREATE TABLE Courses (
    course_id TEXT PRIMARY KEY,
    course_name TEXT,
    credits INTEGER
);

4.Create Semesters Table

CREATE TABLE Semesters (
    semester_id INTEGER PRIMARY KEY,
    semester_name TEXT
);

 5. Create Grades Table

CREATE TABLE Grades (
    grade_id INTEGER PRIMARY KEY AUTOINCREMENT,
    student_id INTEGER,
    course_id TEXT,
    semester_id INTEGER,
    marks INTEGER,
    grade TEXT,
    FOREIGN KEY(student_id) REFERENCES Students(student_id),
    FOREIGN KEY(course_id) REFERENCES Courses(course_id),
    FOREIGN KEY(semester_id) REFERENCES Semesters(semester_id)
);

6. Create GPA Table

CREATE TABLE GPA (
    student_id INTEGER,
    semester_id INTEGER,
    gpa REAL,
    PRIMARY KEY (student_id, semester_id)
);

7. Insert Sample Data into Students and courses and semesters.
8. create cgpa trigger.
9.  Create View for Result Summary

CREATE VIEW SemesterResultSummary AS ...

✅ Final Output
Database ready to track students, grades, and GPA.

Trigger keeps GPA up to date automatically.

View provides a clean summary of academic performance per semester.
