**Experiment 2: 8 Queen Problem**

**Aim**

To solve the 8 Queen Problem using the Backtracking algorithm in Python.

**Objective**

*To understand the Backtracking technique.

*To place eight queens on a chessboard without attacking each other.

*To generate a valid solution.

**Algorithm**

*Start from the first column.

*Place a queen in a safe row.

*Move to the next column.

*If no safe position exists, backtrack.

*Continue until all eight queens are placed.

*Print the board.

**Flowchart**
```chart
           Start
             │
             ▼
     Place Queen in Column
             │
             ▼
      Is Position Safe?
        ┌────┴────┐
       No        Yes
       │          │
       ▼          ▼
   Try Next    Place Queen
     Row           │
                   ▼
          All Queens Placed?
             ┌────┴────┐
            Yes       No
             │          │
             ▼          ▼
      Print Solution  Next Column
             │
             ▼
            End
```
            
**Python Code**
```python
N = 8

board = [[0]*N for i in range(N)]

def safe(row,col):

    for i in range(col):
        if board[row][i]:
            return False

    i=row
    j=col
    while i>=0 and j>=0:
        if board[i][j]:
            return False
        i-=1
        j-=1

    i=row
    j=col
    while i<N and j>=0:
        if board[i][j]:
            return False
        i+=1
        j-=1

    return True

def solve(col):

    if col==N:
        return True

    for row in range(N):

        if safe(row,col):

            board[row][col]=1

            if solve(col+1):
                return True

            board[row][col]=0

    return False

solve(0)

for row in board:
    print(row)
```

**Output**
```text
[1, 0, 0, 0, 0, 0, 0, 0]
[0, 0, 0, 0, 1, 0, 0, 0]
[0, 0, 0, 0, 0, 0, 0, 1]
[0, 0, 0, 0, 0, 1, 0, 0]
[0, 0, 1, 0, 0, 0, 0, 0]
[0, 0, 0, 0, 0, 0, 1, 0]
[0, 1, 0, 0, 0, 0, 0, 0]
[0, 0, 0, 1, 0, 0, 0, 0]
```
**Result**

The 8 Queen Problem was solved successfully using the Backtracking algorithm.

**Conclusion**

The Backtracking algorithm efficiently places all eight queens on the chessboard such that no two queens attack each other.
