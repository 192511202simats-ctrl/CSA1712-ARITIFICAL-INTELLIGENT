
# EX-33. NUMBER OF VOWELS

**AIM**

To find the number of vowels in a given string.

**OBJECTIVE**

1. To accept a string.
2. To identify vowels.
3. To count the total number of vowels.
4. To display the result.

**ALGORITHM**

1. Start.
2. Enter a string.
3. Initialize the vowel count to zero.
4. Read each character.
5. Check whether the character is a vowel.
6. If it is a vowel, increment the count.
7. Display the count.
8. Stop.

**FLOWCHART**

```
START
  ↓
Enter string
  ↓
Set count = 0
  ↓
Read character
  ↓
Is character a vowel?
 ┌──────────┴──────────┐
Yes                    No
 ↓                      ↓
count = count + 1   Continue
 └──────────┬──────────┘
            ↓
     More characters?
       ┌────┴────┐
      Yes        No
       ↓          ↓
   Read next   Display count
   character       ↓
                  STOP
```

**PYTHON CODE**

```python
text = input("Enter a string: ")

vowels = "aeiouAEIOU"
count = 0

for ch in text:
    if ch in vowels:
        count += 1

print("Number of vowels:", count)
```

**SAMPLE OUTPUT**

```
Enter a string: Artificial Intelligence
Number of vowels: 10
```

**RESULT**

The program successfully counts the number of vowels in the given string.

**CONCLUSION**

Thus, the number of vowels in a string was successfully calculated using Python.
