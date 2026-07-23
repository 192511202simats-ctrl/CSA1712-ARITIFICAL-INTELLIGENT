**Experiment 4: Crypt-Arithmetic Problem**

**Aim**

To solve the Crypt-Arithmetic problem using Python.

**Objective**

*To assign unique digits to letters.

*To satisfy the arithmetic equation.

**Algorithm**

*Define the words.

*Assign digits to letters.

*Check uniqueness.

*Verify arithmetic equation.

*Print the valid solution.

**Flowchart**
```
       Start
         |
 Assign Digits
         |
 Check Unique?
   /        \
 No         Yes
 |            |
Retry     Verify Sum
             |
      Correct?
      /      \
    No       Yes
    |          |
 Retry     Display
             |
            Stop
```
**Python Code**
```
from itertools import permutations

letters = ('S','E','N','D','M','O','R','Y')

for p in permutations(range(10),8):

    d = dict(zip(letters,p))

    if d['S']==0 or d['M']==0:
        continue

    send = d['S']*1000+d['E']*100+d['N']*10+d['D']
    more = d['M']*1000+d['O']*100+d['R']*10+d['E']
    money = d['M']*10000+d['O']*1000+d['N']*100+d['E']*10+d['Y']

    if send + more == money:
        print("Solution:")
        print(d)
        print(send,"+",more,"=",money)
        break
```
**Sample Output**
```
Solution:
9567 + 1085 = 10652
```
**Result**

The crypt-arithmetic puzzle was solved successfully.

**Conclusion**

Constraint satisfaction techniques help solve crypt-arithmetic problems efficiently.
