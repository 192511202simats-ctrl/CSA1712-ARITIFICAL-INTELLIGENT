**Experiment-18. Prolog Program for a Database with Name and DOB**

**Aim**

To create a simple database containing names and dates of birth.

**Objective**

To store and retrieve personal details using database facts.

**Algorithm**

Create name and DOB records.

Store the records.

Enter a name to search.

Display the corresponding DOB.

**Flowchart**
```

START
  ↓
Create Database
  ↓
Store Name & DOB
  ↓
Enter Name
  ↓
Search Database
  ↓
Display DOB
  ↓
STOP
```
**Python Code**
```
db = {
    "Arun": "10-05-2004",
    "Bala": "15-08-2003",
    "Kumar": "20-01-2005"
}

name = input("Enter name: ")

if name in db:
    print("DOB =", db[name])
else:
    print("Name not found")
```
**Sample Output**
```
Enter name: Arun
DOB = 10-05-2004
```
**screenshot**
<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/efa9805a-26e4-4677-9369-33f6c71666a6" />


**Result**

The database was successfully created and searched.

**Conclusion**

The program demonstrates storing and retrieving Name-DOB information.
