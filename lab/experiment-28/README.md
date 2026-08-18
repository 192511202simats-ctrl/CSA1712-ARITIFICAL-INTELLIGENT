# EX-28. MEDICAL DIAGNOSIS

**AIM**

To implement a simple rule-based medical diagnosis system.

**OBJECTIVE**

1. To accept symptoms from the user.
2. To compare symptoms with predefined rules.
3. To display a possible condition.

**ALGORITHM**

1. Start.
2. Create disease and symptom rules.
3. Enter symptoms.
4. Compare the symptoms with the rules.
5. Find the condition with the highest match.
6. Display the possible condition.
7. Stop.

**FLOWCHART**

```
START
  ↓
Create symptom rules
  ↓
Enter symptoms
  ↓
Compare with rules
  ↓
Find best match
  ↓
Display possible condition
  ↓
STOP
```

**PYTHON CODE**

```python
rules = {
    "common cold": {"cough", "sneezing", "runny nose"},
    "flu": {"fever", "cough", "body pain"},
    "allergy": {"sneezing", "itching", "runny nose"}
}

symptoms = set(
    x.strip().lower()
    for x in input("Enter symptoms: ").split(",")
)

scores = {}

for disease in rules:
    scores[disease] = len(symptoms & rules[disease])

best = max(scores, key=scores.get)

print("Possible condition:", best)
print("This is only an educational result.")
```

**SAMPLE OUTPUT**

```
Enter symptoms: fever,cough,body pain
Possible condition: flu
This is only an educational result.
```

**RESULT**

The program successfully identifies the condition that best matches the entered symptoms.

**CONCLUSION**

Thus, a simple rule-based medical diagnosis system was successfully implemented.
