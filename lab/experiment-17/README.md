**Experiment-17. Prolog Program to Sum Integers from 1 to N**

**Aim**

To implement a program to find the sum of integers from 1 to N.

**Objective**

To calculate the sum using recursive logic.

**Algorithm**

Read N.

If N = 0, return 0.

Otherwise calculate N + sum(N-1).

Display the sum.

**Flowchart**
```

START
  ↓
Enter N
  ↓
Is N = 0?
 ↙       ↘
YES       NO
 ↓         ↓
Sum=0   N + Sum(N-1)
  ↓         ↓
  └──→ Display Sum
          ↓
         STOP
```
**Python Code**
```
def sum_n(n):
    if n == 0:
        return 0
    return n + sum_n(n - 1)

n = int(input("Enter N: "))
print("Sum =", sum_n(n))

```
**Sample Output**
```
Enter N: 5
Sum = 15
```
**screenshot**
<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/8c7ba04f-8f81-4385-9a3a-898073b3176d" />


**Result**

The sum of integers from 1 to N was successfully calculated.

**Conclusion**

The program demonstrates recursive calculation of the sum of integers.
