# EX-21. TOWERS OF HANOI

**AIM**

To implement the Towers of Hanoi problem using recursion.

**OBJECTIVE**

1. To move `n` disks from source to destination.
2. To use an auxiliary tower.
3. To understand recursive problem solving.

**ALGORITHM**

1. Start.
2. Read the number of disks `n`.
3. If `n = 1`, move the disk from source to destination.
4. Move `n-1` disks from source to auxiliary.
5. Move the largest disk from source to destination.
6. Move `n-1` disks from auxiliary to destination.
7. Stop.

**FLOWCHART**

```
START
  ↓
Read number of disks
  ↓
Is n = 1?
 ┌───────┴───────┐
Yes              No
 ↓                ↓
Move disk     Move n-1 disks
                  ↓
             Move largest disk
                  ↓
             Move n-1 disks
                  ↓
                 STOP
```

**PYTHON CODE**

```python
def hanoi(n, source, auxiliary, destination):
    if n == 1:
        print("Move disk from", source, "to", destination)
        return

    hanoi(n - 1, source, destination, auxiliary)
    print("Move disk from", source, "to", destination)
    hanoi(n - 1, auxiliary, source, destination)

n = int(input("Enter number of disks: "))
hanoi(n, "A", "B", "C")
```

**SAMPLE OUTPUT**

```
Enter number of disks: 3
Move disk from A to C
Move disk from A to B
Move disk from C to B
Move disk from A to C
Move disk from B to A
Move disk from B to C
Move disk from A to C
```
**Screenshot**
<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/9ad786f6-110e-43d7-bdf2-c3be05c285f3" />


**RESULT**

The Towers of Hanoi problem was successfully implemented using recursion.

**CONCLUSION**

Thus, the Towers of Hanoi problem was successfully solved using Python recursion.

