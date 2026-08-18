# EX-23. FAMILY TREE

**AIM**

To implement a family tree using parent-child relationships.

**OBJECTIVE**

1. To represent family relationships.
2. To find parents and children.
3. To implement relationship-based reasoning.

**ALGORITHM**

1. Start.
2. Store parent-child relationships.
3. Enter the person's name.
4. Search for the person's parents.
5. Search for the person's children.
6. Display the relationships.
7. Stop.

**FLOWCHART**

```
START
  ↓
Create family relationships
  ↓
Enter person name
  ↓
Find parents
  ↓
Find children
  ↓
Display relationships
  ↓
STOP
```

**PYTHON CODE**

```python
family = {
    "ravi": ["arun", "meena"],
    "sita": ["arun", "meena"],
    "arun": ["kiran"],
    "meena": ["kiran"]
}

person = input("Enter person name: ").lower()

parents = []

for p in family:
    if person in family[p]:
        parents.append(p)

children = family.get(person, [])

print("Parents:", parents)
print("Children:", children)
```

**SAMPLE OUTPUT**

```
Enter person name: kiran
Parents: ['arun', 'meena']
Children: []
```

**RESULT**

The program successfully displays the family relationships.

**CONCLUSION**

Thus, a simple family tree was successfully implemented using Python.
