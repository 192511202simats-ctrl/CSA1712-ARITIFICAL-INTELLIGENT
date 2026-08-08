**experiment-16. Feed Forward Neural Network**

**Aim**

To implement a simple Feed Forward Neural Network using Python.

**Objective**

To understand how input data passes through input, hidden, and output layers to produce an output.

**Algorithm**

Import NumPy.

Define input, weights, and bias.

Calculate hidden-layer output.

Apply sigmoid activation.

Calculate final output.

Display the result.

**Flowchart**
```
START
  ↓
Enter Input
  ↓
Initialize Weights & Bias
  ↓
Calculate Hidden Layer
  ↓
Apply Activation Function
  ↓
Calculate Output Layer
  ↓
Display Output
  ↓
STOP
```
**Python Code**
```
import numpy as np

x = np.array([[0, 1]])
w1 = np.array([[0.5], [0.5]])
w2 = np.array([[1.0]])
b = 0.0

hidden = 1 / (1 + np.exp(-(x @ w1 + b)))
output = hidden @ w2

print("Output:", output)
```
**Sample Output**
```
Output: [[0.73105858]]
```
**screenshot**
<img width="1917" height="1013" alt="image" src="https://github.com/user-attachments/assets/b61a31c4-ee68-4beb-ba5f-85886a457a08" />


**Result**

The Feed Forward Neural Network was successfully implemented.

**Conclusion**

The program demonstrates how data flows forward through a neural network to produce an output.
