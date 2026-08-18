# EX-27. BEST FIRST SEARCH ALGORITHM

**AIM**

To implement the Best First Search algorithm using heuristic values.

**OBJECTIVE**

1. To understand heuristic search.
2. To select the most promising node.
3. To find a path from the start node to the goal node.

**ALGORITHM**

1. Start.
2. Create the graph and heuristic values.
3. Insert the start node into the priority queue.
4. Select the node with the smallest heuristic value.
5. Check whether it is the goal.
6. If not, add its neighbours.
7. Repeat until the goal is reached.
8. Stop.

**FLOWCHART**

```
START
  ↓
Initialize graph and heuristic
  ↓
Insert start node
  ↓
Select node with lowest heuristic
  ↓
Goal reached?
 ┌──────────┴──────────┐
Yes                    No
 ↓                      ↓
Display path        Add neighbours
 ↓                      ↓
STOP              Select next node
```

**PYTHON CODE**

```python
import heapq

graph = {
    "A": ["B", "C"],
    "B": ["D", "E"],
    "C": ["F"],
    "D": [],
    "E": ["G"],
    "F": ["G"],
    "G": []
}

heuristic = {
    "A": 6,
    "B": 4,
    "C": 5,
    "D": 7,
    "E": 2,
    "F": 3,
    "G": 0
}

def best_first_search(start, goal):
    queue = [(heuristic[start], start, [start])]
    visited = set()

    while queue:
        _, node, path = heapq.heappop(queue)

        if node in visited:
            continue

        visited.add(node)

        if node == goal:
            return path

        for neighbour in graph[node]:
            if neighbour not in visited:
                heapq.heappush(
                    queue,
                    (heuristic[neighbour],
                     neighbour,
                     path + [neighbour])
                )

    return None

path = best_first_search("A", "G")
print("Path:", " -> ".join(path))
```

**SAMPLE OUTPUT**

```
Path: A -> B -> E -> G
```

**RESULT**

The Best First Search algorithm successfully found a path from the start node to the goal node.

**CONCLUSION**

Thus, Best First Search was successfully implemented using heuristic values.

