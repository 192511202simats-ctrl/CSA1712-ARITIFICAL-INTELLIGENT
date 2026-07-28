**11. Map Coloring using CSP**

**Aim**

To implement the Map Coloring Problem using Constraint Satisfaction Problem (CSP).

**Objective**

To assign colors to regions such that no two adjacent regions have the same color.

**Algorithm**

Start.

Define the map and available colors.

Select a region.

Assign a color.

Check constraints with neighboring regions.

If constraints fail, backtrack.

Continue until all regions are colored.

Stop.
**Flowchart**
```
        Start
          |
    Define Regions
          |
   Select Next Region
          |
     Assign Color
          |
Constraints Satisfied?
      /          \
    Yes           No
    |              |
Next Region    Backtrack
    |
All Regions Colored?
     /        \
   No         Yes
   |            |
 Repeat     Display Colors
                 |
                End
```
**Python Code**
```
states = ['A', 'B', 'C', 'D']

neighbors = {
    'A': ['B', 'C'],
    'B': ['A', 'C', 'D'],
    'C': ['A', 'B', 'D'],
    'D': ['B', 'C']
}

colors = ['Red', 'Green', 'Blue']

assignment = {}

def is_safe(state, color):
    for neighbor in neighbors[state]:
        if assignment.get(neighbor) == color:
            return False
    return True

def solve(index):
    if index == len(states):
        return True

    state = states[index]

    for color in colors:
        if is_safe(state, color):
            assignment[state] = color

            if solve(index + 1):
                return True

            del assignment[state]

    return False

if solve(0):
    print("Color Assignment:")
    for state in assignment:
        print(state, ":", assignment[state])
else:
    print("No solution found.")
```
**Output**
```
Color Assignment:
A : Red
B : Green
C : Blue
D : Red
```
**Result**

All regions were successfully colored without violating adjacency constraints.

**Conclusion**

The Map Coloring Problem was solved using the CSP backtracking technique, ensuring that adjacent regions have different colors.
