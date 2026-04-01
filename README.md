# 🎓 Student Database System

## 📌 Description
A PostgreSQL database system that manages student information, majors, and course data.

This project was built as part of my learning journey in SQL and Bash scripting.

## 🛠️ Technologies Used
- PostgreSQL
- SQL
- Bash

## 🧱 Database Structure

### Tables:
- students
- majors
- courses
- majors_courses (junction table)

### Relationships:
- A student belongs to a major
- A major can have multiple courses
- Many-to-many relationship between majors and courses

## 🧪 Example Queries

### Get all students with their majors
```sql
SELECT students.name, majors.major
FROM students
JOIN majors ON students.major_id = majors.major_id;
```

## 📊 Sample Output

| Student Name | Major        |
|-------------|-------------|
| John Doe    | Computer Sci |
| Jane Smith  | Biology      |

### Get courses per major
```sql
SELECT major, course
FROM majors
JOIN majors_courses USING(major_id)
JOIN courses USING(course_id);
```

## ▶️ How to Run

1. Import database:
```bash
psql -U postgres -f student.sql
```

2. Run script:
```bash
bash insert_data.sh
```
## 📈 Data Analysis

### Number of students per major
SELECT major, COUNT(*) 
FROM students
JOIN majors USING(major_id)
GROUP BY major;

### Most popular courses
SELECT course, COUNT(*) 
FROM majors_courses
JOIN courses USING(course_id)
GROUP BY course
ORDER BY COUNT DESC;

## 📊 Sample Output

| Major        | Number of Students |
|--------------|-------------------|
| Computer Sci | 5                 |
| Biology      | 3                 |

## 🎯 Purpose
This project demonstrates how relational databases are used to organize and analyze structured data, similar to real-world student management systems.

## 📁 Project Structure

### Part 1
- Database creation
- Table setup
- Initial data insertion

### Part 2
- Advanced queries
- Data retrieval using JOIN
- Improved database logic

## 📚 What I Learned
- Relational database design
- Foreign keys and relationships
- JOIN operations
- Bash + SQL integration

## 🚀 Future Improvements
- Add more complex queries (analytics)
- Create reports (top students, etc.)
- Connect to a frontend app

