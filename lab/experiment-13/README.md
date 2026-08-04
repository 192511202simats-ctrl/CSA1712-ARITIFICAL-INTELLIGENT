**Experiment 13: Minimax Algorithm for Gaming**
**Aim**

To implement the Minimax algorithm using Python.

**Objective**

To determine the best possible move in a two-player game.

**Algorithm**

Start.

Generate all possible moves.

Evaluate terminal states.

Max player chooses maximum score.

Min player chooses minimum score.

Return best move.

Stop.

**Flowchart**
```
Start
  |
Generate Moves
  |
Terminal?
 /   \
Yes   No
 |     |
Score Max/Min
 |     |
Return Best Move
 |
End
```
**Python Code**
```
def minimax(depth, isMax):
    if depth == 3:
        return depth

    if isMax:
        return max(minimax(depth+1, False),
                   minimax(depth+1, False))
    else:
        return min(minimax(depth+1, True),
                   minimax(depth+1, True))

print("Optimal Value:", minimax(0, True))
```
**Output**
```
Optimal Value: 3
```
**screenshot**

<img width="1917" height="1013" alt="image" src="https://github.com/user-attachments/assets/6588e0af-5e61-4b23-9927-48685683a687" />

**Result**

The optimal move value was computed successfully.

**Conclusion**

Minimax evaluates all game possibilities and selects the best move.
