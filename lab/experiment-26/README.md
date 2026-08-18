# EX-26. FRUIT AND ITS COLOR USING BACKTRACKING

**AIM**

To find the color of a fruit using backtracking.

**OBJECTIVE**

1. To store fruit-color relationships.
2. To search for a particular fruit.
3. To use backtracking when a match is not found.

**ALGORITHM**

1. Start.
2. Store fruit and color facts.
3. Enter the fruit name.
4. Check the current fruit.
5. If matched, display its color.
6. Otherwise, move to the next fact.
7. Continue until the fruit is found.
8. Stop.

**FLOWCHART**

```
START
  ↓
Create fruit-color facts
  ↓
Enter fruit
  ↓
Check current fact
  ↓
Match found?
 ┌─────────┴─────────┐
Yes                   No
 ↓                     ↓
Display color      Check next fact
 └─────────┬─────────┘
           ↓
          STOP
```

**PYTHON CODE**

```python
facts = [
    ("apple", "red"),
    ("banana", "yellow"),
    ("orange", "orange"),
    ("grape", "purple"),
    ("guava", "green")
]

def find_color(fruit, index=0):
    if index == len(facts):
        return None

    if facts[index][0] == fruit:
        return facts[index][1]

    return find_color(fruit, index + 1)

fruit = input("Enter fruit: ").lower()
color = find_color(fruit)

if color:
    print("Color:", color)
else:
    print("Fruit not found")
```

**SAMPLE OUTPUT**

```
Enter fruit: banana
Color: yellow
```

**RESULT**

The program successfully finds the color of the given fruit.

**CONCLUSION**

Thus, fruit-color matching was successfully implemented using backtracking.

