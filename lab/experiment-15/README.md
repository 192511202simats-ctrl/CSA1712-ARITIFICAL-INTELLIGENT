**Experiment 15: Decision Tree**

**Aim**

To implement a Decision Tree classifier using Python.

**Objective**

To classify data using a Decision Tree algorithm.

**Algorithm**


Import libraries.

Load dataset.

Split data.

Train Decision Tree.

Predict output.

Display accuracy.

**Flowchart**
```
Start
 |
Load Dataset
 |
Split Data
 |
Train Model
 |
Predict
 |
Display Accuracy
 |
End
```
**Python Code**
```
from sklearn.tree import DecisionTreeClassifier

X = [[0], [1], [2], [3]]
Y = [0, 0, 1, 1]

model = DecisionTreeClassifier()
model.fit(X, Y)

print(model.predict([[1.5]]))
```
**Output**
```
[0]
```
**Result**

The Decision Tree classifier successfully predicted the class label.

**Conclusion**

Decision Trees are effective for classification problems.
