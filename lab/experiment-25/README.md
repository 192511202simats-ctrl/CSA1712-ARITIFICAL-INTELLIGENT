# EX-25. MONKEY BANANA PROBLEM

**AIM**

To implement the Monkey Banana problem using state-space representation.

**OBJECTIVE**

1. To represent the initial state.
2. To perform the required actions.
3. To reach the goal state.
4. To demonstrate problem-solving techniques.

**ALGORITHM**

1. Start.
2. Place the monkey on the floor.
3. Move the box below the banana.
4. Climb onto the box.
5. Reach the banana.
6. Grab the banana.
7. Stop.

**FLOWCHART**

```
START
  ↓
Monkey on floor
  ↓
Move box below banana
  ↓
Climb box
  ↓
Reach banana
  ↓
Grab banana
  ↓
GOAL ACHIEVED
  ↓
STOP
```

**PYTHON CODE**

```python
monkey = "floor"
box = "away"

print("Initial State")
print("Monkey:", monkey)
print("Box:", box)

print("Move box below banana")
box = "below banana"

print("Monkey climbs box")
monkey = "on box"

if monkey == "on box" and box == "below banana":
    print("Monkey grabs banana")
    print("Goal achieved")
else:
    print("Goal not achieved")
```

**SAMPLE OUTPUT**

```
Initial State
Monkey: floor
Box: away
Move box below banana
Monkey climbs box
Monkey grabs banana
Goal achieved
```
**Screenshot**
<img width="1919" height="1018" alt="image" src="https://github.com/user-attachments/assets/7123e94c-40ae-4b2e-a187-4198a1090c12" />



**RESULT**

The Monkey Banana problem was successfully solved using state transitions.

**CONCLUSION**

Thus, the Monkey Banana problem was successfully implemented in Python.
