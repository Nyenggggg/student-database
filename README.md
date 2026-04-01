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
## 📈 Analysis Queries

### Top majors by number of students
SELECT major, COUNT(*) 
FROM students
JOIN majors USING(major_id)
GROUP BY major
ORDER BY COUNT DESC;

## 📚 What I Learned
- Relational database design
- Foreign keys and relationships
- JOIN operations
- Bash + SQL integration

## 🚀 Future Improvements
- Add more complex queries (analytics)
- Create reports (top students, etc.)
- Connect to a frontend app

