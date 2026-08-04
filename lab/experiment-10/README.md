**Experiment 10: A'*' Algorithm**

**Aim**

To implement the A* Search Algorithm using Python.

**Objective**

To find the shortest path between two nodes using heuristic values.

**Algorithm**

Start.

Initialize open and closed lists.

Add the source node to the open list.

Select the node with minimum f(n).

If destination is reached, stop.

Otherwise, expand neighboring nodes.

Update costs and parent nodes.

Repeat until destination is reached.

**Flowchart**
```
       Start
         |
Initialize Open List
         |
Select Lowest f(n)
         |
Goal Reached?
    /      \
  Yes       No
  |          |
Display     Expand
 Path       Neighbors
              |
 Update Costs
              |
           Repeat
```
**Python Code**
```
import heapq

graph = {
    'A': [('B', 1), ('C', 3)],
    'B': [('D', 3), ('E', 1)],
    'C': [('F', 5)],
    'D': [],
    'E': [('F', 2)],
    'F': []
}

heuristic = {
    'A': 6,
    'B': 4,
    'C': 4,
    'D': 2,
    'E': 2,
    'F': 0
}

def astar(start, goal):
    queue = [(0, start)]
    cost = {start: 0}
    parent = {start: None}

    while queue:
        _, current = heapq.heappop(queue)

        if current == goal:
            break

        for neighbor, weight in graph[current]:
            new_cost = cost[current] + weight

            if neighbor not in cost or new_cost < cost[neighbor]:
                cost[neighbor] = new_cost
                priority = new_cost + heuristic[neighbor]
                heapq.heappush(queue, (priority, neighbor))
                parent[neighbor] = current

    path = []
    node = goal

    while node:
        path.append(node)
        node = parent[node]

    return path[::-1]

print("Shortest Path:", astar('A', 'F'))
```
**Output**
```
Shortest Path:
['A', 'B', 'E', 'F']
```
**screenshot**

<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/6cabdfd7-f42e-44a6-847c-16f730bee57d" />

**Result**

The shortest path was successfully found using the A* algorithm.

**Conclusion**

A* efficiently finds the optimal path using both path cost and heuristic information.
