**Experiment 3: Water Jug Problem**

**Aim**

To solve the Water Jug Problem using State Space Search in Python.

**Objective**

*To obtain the required quantity of water using two jugs.

*To understand state-space representation and search algorithms.

**Algorithm**
*Start with two empty jugs.

*Fill either jug.

*Empty either jug.

*Pour water from one jug to another until one becomes empty or the other becomes full.

*Repeat until the target amount is reached.

*Display all intermediate states.

**Flowchart**
```
          Start
             |
      Initialize Jugs
             |
      Goal Reached?
       /          \
     Yes          No
      |            |
 Display State  Perform
      |         Fill/Empty/
      |          Transfer
      |            |
      +------------+
             |
            Stop
```
**Python Code**
```
from collections import deque

def water_jug(cap1, cap2, target):
    visited = set()
    queue = deque([((0, 0), [])])

    while queue:
        (a, b), path = queue.popleft()

        if (a, b) in visited:
            continue

        visited.add((a, b))
        path = path + [(a, b)]

        if a == target or b == target:
            return path

        next_states = [
            (cap1, b),
            (a, cap2),
            (0, b),
            (a, 0),
            (max(0, a-(cap2-b)), min(cap2, b+a)),
            (min(cap1, a+b), max(0, b-(cap1-a)))
        ]

        for state in next_states:
            if state not in visited:
                queue.append((state, path))

    return None

solution = water_jug(4,3,2)

print("Steps:")
for step in solution:
    print(step)
```
**Sample Output**
```
Steps:
(0, 0)
(0, 3)
(3, 0)
(3, 3)
(4, 2)
```
**Result**

The required amount of water was obtained successfully.

**Conclusion**

The Water Jug Problem was solved using state-space search by exploring valid states.
