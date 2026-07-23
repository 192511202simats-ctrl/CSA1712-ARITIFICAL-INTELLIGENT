**Experiment 6: Vacuum Cleaner Problem**

**Aim**

To implement a simple Vacuum Cleaner Agent in Python.

**Objective**

*To clean dirty rooms automatically.

*To understand intelligent agent behavior.
**Algorithm**

*Read room status.

*If room is dirty, clean it.

*Move to next room.

*Repeat until all rooms are clean.

*Stop execution.

**Flowchart**
```
         Start
           |
     Read Room State
           |
     Room Dirty?
      /        \
    Yes        No
     |          |
 Clean Room   Next Room
      \         /
       Continue
           |
 All Rooms Clean?
      /        \
    Yes        No
     |          |
   Stop      Repeat
```
**Python Code**
```
rooms = {
    "A":"Dirty",
    "B":"Dirty"
}

for room in rooms:

    print("Room",room,"is",rooms[room])

    if rooms[room]=="Dirty":
        print("Cleaning Room",room)
        rooms[room]="Clean"

print("\nFinal Room Status")

for room in rooms:
    print(room,"=",rooms[room])
```
**Sample Output**
```
Room A is Dirty
Cleaning Room A

Room B is Dirty
Cleaning Room B

Final Room Status

A = Clean
B = Clean
```
**Result**

The vacuum cleaner agent successfully cleaned all dirty rooms.

**Conclusion**

The vacuum cleaner agent demonstrated simple reflex-agent behavior by sensing the environment and performing appropriate cleaning actions.
