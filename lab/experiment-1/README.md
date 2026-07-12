**Experiment 1: 8 Puzzle Problem**

**Aim**

To solve the 8 Puzzle Problem using the Breadth-First Search (BFS) algorithm in Python.

**Objective**

*To understand the state-space search technique.

*To implement the Breadth-First Search (BFS) algorithm.

*To find the shortest path from the initial state to the goal state.

**Algorithm**

*Define the initial state and the goal state.

*Store the initial state in a queue.

*Remove the first state from the queue.

*If it matches the goal state, stop.

*Otherwise, generate all possible next states.

*Add unvisited states to the queue.

*Repeat until the goal state is found.

**Flowchart**

            Start
              │
              ▼
      Define Initial State
              │
              ▼
         Add to Queue
              │
              ▼
      Remove First State
              │
              ▼
     Is Goal State Reached?
         ┌────┴────┐
        Yes        No
         │          │
         ▼          ▼
     Display     Generate
     Solution   Next States
         │          │
         └────┬─────┘
              ▼
          Add to Queue
              │
              ▼
             End
             
**Python Code**

```python
from collections import deque

# Goal State
goal = [1, 2, 3,
        4, 5, 6,
        7, 8, 0]

# Possible Moves
moves = {
    0: [1, 3],
    1: [0, 2, 4],
    2: [1, 5],
    3: [0, 4, 6],
    4: [1, 3, 5, 7],
    5: [2, 4, 8],
    6: [3, 7],
    7: [4, 6, 8],
    8: [5, 7]
}

# Generate Next States
def next_state(state):
    zero = state.index(0)
    result = []

    for move in moves[zero]:
        new = state[:]
        new[zero], new[move] = new[move], new[zero]
        result.append(new)

    return result

# Breadth-First Search
def bfs(start):
    queue = deque()
    queue.append((start, []))
    visited = []

    while queue:
        state, path = queue.popleft()

        if state == goal:
            return path + [state]

        if state not in visited:
            visited.append(state)

            for s in next_state(state):
                if s not in visited:
                    queue.append((s, path + [state]))

    return None

# Initial State
start = [1, 2, 3,
         4, 5, 6,
         0, 7, 8]

# Solve Puzzle
solution = bfs(start)

# Display Solution
print("Solution Steps:\n")

if solution:
    for step in solution:
        print(step[0:3])
        print(step[3:6])
        print(step[6:9])
        print()
else:
    print("No solution found.")
```
    
**Output**

```text
Solution Steps:

[1, 2, 3]
[4, 5, 6]
[0, 7, 8]

[1, 2, 3]
[4, 5, 6]
[7, 0, 8]

[1, 2, 3]
[4, 5, 6]
[7, 8, 0]
```

**Result**

The 8 Puzzle Problem was solved successfully using the Breadth-First Search algorithm.

**Conclusion**

The BFS algorithm successfully finds the shortest sequence of moves from the initial state to the goal state.
