# EX-29. FORWARD CHAINING

**AIM**

To implement forward chaining using facts and rules.

**OBJECTIVE**

1. To start with known facts.
2. To apply rules to derive new facts.
3. To perform data-driven reasoning.

**ALGORITHM**

1. Start.
2. Initialize the known facts.
3. Create rules.
4. Check whether rule conditions are satisfied.
5. Add the conclusion as a new fact.
6. Repeat until no new facts are generated.
7. Check the query.
8. Stop.

**FLOWCHART**

```
START
  ↓
Initialize facts
  ↓
Check rules
  ↓
Conditions satisfied?
 ┌──────────┴──────────┐
Yes                    No
 ↓                      ↓
Add new fact       Check next rule
 ↓                      ↓
Repeat until no new facts
  ↓
Check query
  ↓
STOP
```

**PYTHON CODE**

```python
facts = {"rainy", "cloudy"}

rules = [
    ({"rainy"}, "wet_ground"),
    ({"wet_ground"}, "slippery"),
    ({"slippery", "cloudy"}, "drive_carefully")
]

changed = True

while changed:
    changed = False

    for conditions, conclusion in rules:
        if conditions.issubset(facts):
            if conclusion not in facts:
                facts.add(conclusion)
                print("Derived:", conclusion)
                changed = True

query = input("Enter query: ").lower()

if query in facts:
    print("Query is TRUE")
else:
    print("Query is FALSE")
```

**SAMPLE OUTPUT**

```
Derived: wet_ground
Derived: slippery
Derived: drive_carefully
Enter query: slippery
Query is TRUE
```

**RESULT**

The program successfully derived new facts using forward chaining.

**CONCLUSION**

Thus, forward chaining was successfully implemented using Python.
