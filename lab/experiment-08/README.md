**Experiment 8: Depth First Search (DFS)**

**Aim**

To implement the Depth First Search (DFS) algorithm using Python.

**Objective**

To traverse all vertices of a graph using recursion.

**Algorithm**

Start.

Create the graph.

Select the starting node.

Mark the node as visited.

Print the node.

Recursively visit all unvisited adjacent nodes.

Stop.

**Flowchart**
```
       Start
         |
    Create Graph
         |
 Select Start Node
         |
Mark as Visited
         |
 Print Node
         |
Any Unvisited Neighbor?
      /       \
    Yes        No
     |          |
Recursive DFS  Return
     |
    End
```
**Python Code**
```
graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': ['F'],
    'F': []
}

visited = set()

def dfs(node):
    if node not in visited:
        print(node, end=" ")
        visited.add(node)

        for neighbor in graph[node]:
            dfs(neighbor)

print("DFS Traversal:")
dfs('A')
```
**Output**
```
DFS Traversal:
A B D E F C
```
**Result**

The graph was successfully traversed using the DFS algorithm.

**Conclusion**

DFS explores one branch completely before moving to another branch using recursion or a stack.
