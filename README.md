grades, calculating GPA, and summarizing semester results. It includes tables for students, courses, semesters, grades, and GPA. The system also integrates triggers and views for automation and reporting.

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
