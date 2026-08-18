
# EX-32. PATTERN MATCHING

**AIM**

To implement pattern matching in a given string.

**OBJECTIVE**

1. To read a text.
2. To read a pattern.
3. To search for the pattern.
4. To display whether the pattern is found.

**ALGORITHM**

1. Start.
2. Enter the text.
3. Enter the pattern.
4. Search for the pattern in the text.
5. If found, display its position.
6. Otherwise, display "Pattern not found".
7. Stop.

**FLOWCHART**

```
START
  ↓
Enter text
  ↓
Enter pattern
  ↓
Search pattern
  ↓
Pattern found?
 ┌──────────┴──────────┐
Yes                    No
 ↓                      ↓
Display position    Pattern not found
 └──────────┬──────────┘
            ↓
           STOP
```

**PYTHON CODE**

```python
text = input("Enter text: ")
pattern = input("Enter pattern: ")

position = text.find(pattern)

if position != -1:
    print("Pattern found at position:", position)
else:
    print("Pattern not found")
```

**SAMPLE OUTPUT**

```
Enter text: Artificial Intelligence
Enter pattern: Intelligence
Pattern found at position: 11
```
**Screenshot**
<img width="1915" height="1016" alt="image" src="https://github.com/user-attachments/assets/e6b8acd3-4a23-4132-a77a-56b36e2fd62b" />


**RESULT**

The program successfully finds the given pattern in the text.

**CONCLUSION**

Thus, pattern matching was successfully implemented using Python.

