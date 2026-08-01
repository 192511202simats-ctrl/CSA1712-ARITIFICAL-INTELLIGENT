**Experiment 7: Breadth First Search (BFS)**

**Aim**

To implement the Breadth First Search (BFS) algorithm using Python.

**Objective**

To traverse all the vertices of a graph level by level starting from a given source node.

**Algorithm**

Start.

Create a graph using an adjacency list.


Initialize an empty queue.

Mark the starting node as visited.

Insert the starting node into the queue.


Repeat until the queue becomes empty:

Remove the front node from the queue.

Print the node.

Visit all adjacent unvisited nodes.

Mark them as visited and insert them into the queue.

Stop.

**Flowchart**
```
        Start
          |
      Create Graph
          |
   Select Start Node
          |
 Add Node to Queue &
   Mark as Visited
          |
   Queue Empty?
     /        \
   No          Yes
   |             |
Remove Front     End
   |
Print Node
   |
Visit Adjacent Nodes
   |
Mark Visited &
Add to Queue
   |
Repeat
```
**Python Code**
```
from collections import deque

graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': ['F'],
    'F': []
}

visited = set()
queue = deque(['A'])

visited.add('A')

print("BFS Traversal:")

while queue:
    node = queue.popleft()
    print(node, end=" ")

    for neighbor in graph[node]:
        if neighbor not in visited:
            visited.add(neighbor)
            queue.append(neighbor)
```
**Output**
```
BFS Traversal:
A B C D E F
```
**Result**

The graph was successfully traversed using the BFS algorithm.

**Conclusion**

BFS visits all vertices level by level using a queue and guarantees the shortest path in an unweighted graph.
