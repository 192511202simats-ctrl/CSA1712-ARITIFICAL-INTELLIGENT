# EX-30. BACKWARD CHAINING

**AIM**

To implement backward chaining using facts and rules.

**OBJECTIVE**

1. To start with a goal.
2. To search for rules that can prove the goal.
3. To implement goal-driven reasoning.

**ALGORITHM**

1. Start.
2. Enter the goal.
3. Check whether the goal is already a fact.
4. Search for a rule that concludes the goal.
5. Check all conditions of the rule recursively.
6. If all conditions are true, prove the goal.
7. Otherwise, the goal cannot be proved.
8. Stop.

**FLOWCHART**

```
START
  ↓
Enter goal
  ↓
Is goal a fact?
 ┌──────────┴──────────┐
Yes                    No
 ↓                      ↓
Goal proved        Find matching rule
                        ↓
                  Check conditions
                        ↓
                  Conditions true?
                   ┌────┴────┐
                  Yes        No
                   ↓          ↓
               Goal proved  Not proved
                   ↓          ↓
                  STOP       STOP
```

**PYTHON CODE**

```python
facts = {"rainy", "cloudy"}

rules = [
    ({"rainy"}, "wet_ground"),
    ({"wet_ground"}, "slippery"),
    ({"slippery", "cloudy"}, "drive_carefully")
]

def prove(goal):
    if goal in facts:
        return True

    for conditions, conclusion in rules:
        if conclusion == goal:
            if all(prove(condition) for condition in conditions):
                return True

    return False

query = input("Enter goal: ").lower()

if prove(query):
    print("Goal can be proved")
else:
    print("Goal cannot be proved")
```

**SAMPLE OUTPUT**

```
Enter goal: drive_carefully
Goal can be proved
```

**RESULT**

The program successfully proves the given goal using backward chaining.

**CONCLUSION**

Thus, backward chaining was successfully implemented using recursive reasoning.

