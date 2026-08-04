**Experiment 12: Tic Tac Toe Game (Python)**

**Aim**

To implement the Tic Tac Toe game using Python.

**Objective**

To develop a two-player Tic Tac Toe game that allows players to take turns until one player wins or the game ends in a draw.

**Algorithm**

Start.

Create a 3×3 board.

Display the board.

Player X enters a position.

Validate the move.

Update the board.

Check for a winner or draw.

Switch to Player O.

Repeat until game ends.

Stop.

**Flowchart**
```
        Start
          |
   Create Empty Board
          |
     Display Board
          |
   Player Enters Move
          |
     Valid Move?
     /        \
   No          Yes
   |             |
Enter Again   Update Board
                  |
        Winner/Draw?
           /      \
         Yes       No
         |          |
      Display     Change
      Result      Player
         |          |
         End     Repeat
```
**Python Code**
```
board = [' ']*9

def display():
    print(board[0], "|", board[1], "|", board[2])
    print("--+---+--")
    print(board[3], "|", board[4], "|", board[5])
    print("--+---+--")
    print(board[6], "|", board[7], "|", board[8])

player = 'X'

for _ in range(9):
    display()
    pos = int(input("Enter position (0-8): "))
    if board[pos] == ' ':
        board[pos] = player
        player = 'O' if player == 'X' else 'X'
    else:
        print("Position already occupied!")

display()
```
**Output**
```
  |   | 
--+---+--
  |   | 
--+---+--
  |   |
```
**screenshot**

<img width="1913" height="1011" alt="image" src="https://github.com/user-attachments/assets/101029ac-922f-484a-8287-341a84c7727b" />

**Result**

The Tic Tac Toe game was implemented successfully.

**Conclusion**

The game allows two players to play alternately until completion.
