**Experiment 14: Alpha-Beta Pruning Algorithm**

**Aim**

To implement Alpha-Beta Pruning using Python.

**Objective**

To optimize the Minimax algorithm by pruning unnecessary branches.

**Algorithm**

Start.

Initialize alpha and beta.

Traverse the game tree.

Update alpha/beta.

Prune branches when alpha ≥ beta.

Return optimal value.

Stop.

**Flowchart**
```
Start
 |
Initialize α, β
 |
Expand Node
 |
α ≥ β ?
 /     \
Yes     No
 |        |
Prune  Continue
 |
Return Result
 |
End
```
**Python Code**
```
def alphabeta(depth, alpha, beta, isMax):
    if depth == 3:
        return depth

    if isMax:
        value = -999
        for _ in range(2):
            value = max(value, alphabeta(depth+1, alpha, beta, False))
            alpha = max(alpha, value)
            if alpha >= beta:
                break
        return value
    else:
        value = 999
        for _ in range(2):
            value = min(value, alphabeta(depth+1, alpha, beta, True))
            beta = min(beta, value)
            if alpha >= beta:
                break
        return value

print(alphabeta(0, -999, 999, True))
```
**Output**
```
3
```
**screenshot**

<img width="1913" height="1017" alt="image" src="https://github.com/user-attachments/assets/554784d0-1b13-4434-b792-93ab168a22d5" />

**Result**

The optimal value was obtained using Alpha-Beta pruning.

**Conclusion**

Alpha-Beta pruning reduces the number of nodes evaluated while producing the same optimal result as Minimax.
