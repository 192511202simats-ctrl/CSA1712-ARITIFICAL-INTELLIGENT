**Experiment-20. Prolog Program for PLANETS Database**

**Aim**

To create a database containing information about planets.

**Objective**

To store and retrieve planet information using database facts.

**Algorithm**

Create a list of planets.

Store the planet names.

Enter a planet name.

Search the database.

Display whether the planet exists.

**Flowchart**
```
START
  ↓
Create Planet Database
  ↓
Enter Planet Name
  ↓
Search Database
  ↓
Is Planet Found?
 ↙          ↘
YES          NO
 ↓            ↓
Found     Not Found
  ↓            ↓
  └────→  Display Result
             ↓
            STOP
```

**Python Code**
```
planets = [
    "Mercury", "Venus", "Earth", "Mars",
    "Jupiter", "Saturn", "Uranus", "Neptune"
]

p = input("Enter planet: ")

if p in planets:
    print(p, "is in the database")
else:
    print("Planet not found")
```
**Sample Output**
```
Enter planet: Earth
Earth is in the database
```
**screenshot**
<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/eabe5cce-6479-4726-9012-ddf172ec075c" />

**Result**

The planet database was successfully created and searched.

**Conclusion**

The program demonstrates basic database storage and searching of planet information.
