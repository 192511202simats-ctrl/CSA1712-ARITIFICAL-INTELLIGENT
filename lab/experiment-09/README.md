**Experiment 9:Travelling Salesman Problem (TSP)**

**Aim**

To implement the Travelling Salesman Problem using Python.

**Objective**

To find the minimum cost path that visits every city exactly once and returns to the starting city.

**Algorithm**

Start.

Define the distance matrix.

Generate all possible city permutations.

Calculate the total cost of each route.

Store the minimum cost.

Display the shortest path.

Stop.

**Flowchart**
```
      Start
        |
Create Distance Matrix
        |
Generate All Routes
        |
Calculate Route Cost
        |
Is Cost Minimum?
    /        \
  Yes         No
   |           |
Update Cost    Next Route
        |
 All Routes Checked?
      /      \
    No        Yes
    |          |
Repeat      Display Result
               |
              End
Python Code
from itertools import permutations

graph = [
    [0, 10, 15, 20],
    [10, 0, 35, 25],
    [15, 35, 0, 30],
    [20, 25, 30, 0]
]

cities = [0, 1, 2, 3]

min_cost = float('inf')
best_path = None

for path in permutations(cities[1:]):
    current_path = [0] + list(path) + [0]
    cost = 0

    for i in range(len(current_path)-1):
        cost += graph[current_path[i]][current_path[i+1]]

    if cost < min_cost:
        min_cost = cost
        best_path = current_path

print("Best Path:", best_path)
print("Minimum Cost:", min_cost)
```
**Output**
```
Best Path: [0, 1, 3, 2, 0]
Minimum Cost: 80
```
**Result**

The shortest route and minimum travel cost were obtained.

**Conclusion**

The Travelling Salesman Problem was solved by checking all possible routes and selecting the one with the minimum cost.
