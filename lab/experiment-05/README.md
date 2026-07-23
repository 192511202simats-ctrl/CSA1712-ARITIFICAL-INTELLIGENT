**Experiment 5: Missionaries and Cannibals Problem**

**Aim**

To solve the Missionaries and Cannibals Problem using Python.

**Objective**

*To safely move all missionaries and cannibals across the river.

*To satisfy all problem constraints.

**Algorithm**

*Start with all missionaries and cannibals on one side.

*Move one or two people.

*Ensure missionaries are never outnumbered.

*Continue until everyone reaches the opposite side.

*Display the solution path.

**Flowchart**
```
        Start
          |
 Initialize State
          |
 Goal?
 /      \
Yes      No
 |        |
Print   Generate
Path    Valid Moves
          |
      Safe State?
      /        \
    No         Yes
    |            |
 Ignore      Add State
      \        /
        Repeat
          |
         Stop
```
**Python Code**
```
from collections import deque

def solve():
    start = (3,3,1)
    goal = (0,0,0)

    moves = [(1,0),(2,0),(0,1),(0,2),(1,1)]

    queue = deque([(start,[start])])
    visited = set()

    while queue:

        state,path = queue.popleft()

        if state == goal:
            return path

        if state in visited:
            continue

        visited.add(state)

        m,c,b = state

        for dm,dc in moves:

            if b==1:
                nm,nc = m-dm,c-dc
                nb = 0
            else:
                nm,nc = m+dm,c+dc
                nb = 1

            if 0<=nm<=3 and 0<=nc<=3:

                if (nm==0 or nm>=nc) and ((3-nm)==0 or (3-nm)>=(3-nc)):
                    queue.append(((nm,nc,nb),path+[(nm,nc,nb)]))

solution = solve()

print("Solution Path")

for s in solution:
    print(s)
```
**Sample Output**
```
Solution Path

(3,3,1)
(3,1,0)
(3,2,1)
...
(0,0,0)
```
**Result**

All missionaries and cannibals crossed the river safely.

**Conclusion**

The state-space search algorithm successfully solved the Missionaries and Cannibals problem.
