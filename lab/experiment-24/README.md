# EX-24. DIET SUGGESTION BASED ON DISEASE

**AIM**

To suggest a general diet based on the given disease using rule-based reasoning.

**OBJECTIVE**

1. To store disease and diet rules.
2. To accept a disease as input.
3. To display the corresponding diet suggestion.

**ALGORITHM**

1. Start.
2. Create disease-diet rules.
3. Enter the disease.
4. Search for the disease in the knowledge base.
5. Display the corresponding diet.
6. If not found, display "No diet rule found".
7. Stop.

**FLOWCHART**

```
START
  ↓
Create disease rules
  ↓
Enter disease
  ↓
Disease found?
 ┌──────────┴──────────┐
Yes                    No
 ↓                      ↓
Display diet       No rule found
 └──────────┬──────────┘
            ↓
           STOP
```

**PYTHON CODE**

```python
diet = {
    "diabetes": "Eat vegetables and controlled carbohydrates",
    "hypertension": "Eat low-sodium foods and vegetables",
    "anemia": "Eat iron-rich foods",
    "obesity": "Eat balanced meals with controlled portions"
}

disease = input("Enter disease: ").lower()

if disease in diet:
    print("Diet suggestion:", diet[disease])
else:
    print("No diet rule found")
```

**SAMPLE OUTPUT**

```
Enter disease: anemia
Diet suggestion: Eat iron-rich foods
```

**RESULT**

The program successfully suggests a general diet according to the disease.

**CONCLUSION**

Thus, a rule-based diet suggestion system was successfully implemented.
