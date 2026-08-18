# EX-22. BIRD CAN FLY OR NOT

**AIM**

To determine whether a particular bird can fly using facts and rules.

**OBJECTIVE**

1. To store bird information.
2. To check the flying ability of a bird.
3. To implement simple rule-based reasoning.

**ALGORITHM**

1. Start.
2. Enter the bird name.
3. Store a list of flying birds.
4. Check whether the entered bird exists in the list.
5. If found, display that the bird can fly.
6. Otherwise, display that the bird cannot fly.
7. Stop.

**FLOWCHART**

```
START
  ↓
Enter bird name
  ↓
Check bird
  ↓
Is bird in flying list?
 ┌──────────┴──────────┐
Yes                    No
 ↓                      ↓
Can Fly              Cannot Fly
 └──────────┬──────────┘
            ↓
           STOP
```

**PYTHON CODE**

```python
flying_birds = [
    "eagle", "sparrow", "parrot",
    "pigeon", "crow", "duck"
]

bird = input("Enter bird name: ").lower()

if bird in flying_birds:
    print(bird, "can fly")
else:
    print(bird, "cannot fly")
```

**SAMPLE OUTPUT**

```
Enter bird name: eagle
eagle can fly
```
**Screenshot**
<img width="1916" height="1020" alt="image" src="https://github.com/user-attachments/assets/e40ba827-e950-414e-a201-118ae08ad52e" />


**RESULT**

The program successfully determines whether the given bird can fly.

**CONCLUSION**

Thus, bird flying ability was successfully implemented using Python rules.

