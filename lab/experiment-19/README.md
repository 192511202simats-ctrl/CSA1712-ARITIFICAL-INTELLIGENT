**Experiment-19. Prolog Program for STUDENT-TEACHER-SUB-CODE**

**Aim**

To create a database representing students, teachers, and subject codes.

**Objective**

To retrieve the teacher and subject information related to a student.

**Algorithm**

Create student records.

Create teacher records.

Create subject-code records.

Search for a student.

Display the related details.

**Flowchart**
```
START
  ↓
Create Student Database
  ↓
Create Teacher Database
  ↓
Create Subject Database
  ↓
Enter Student
  ↓
Search Records
  ↓
Display Details
  ↓
STOP
```

**Python Code**
```
student = {
    "Arun": ("Ravi", "CS101"),
    "Bala": ("Kumar", "CS102"),
    "Kavi": ("Priya", "CS103")
}

name = input("Enter student name: ")

if name in student:
    teacher, code = student[name]
    print("Teacher =", teacher)
    print("Subject Code =", code)
else:
    print("Student not found")
```
**Sample Output**
```
Enter student name: Arun
Teacher = Ravi
Subject Code = CS101
```
**screenshot**
<img width="1916" height="1011" alt="image" src="https://github.com/user-attachments/assets/ded6e722-64aa-4046-a74e-8ae4e17b93c4" />

**Result**

The student-teacher-subject database was successfully implemented.

**Conclusion**

The program demonstrates relationships between students, teachers, and subject codes.
