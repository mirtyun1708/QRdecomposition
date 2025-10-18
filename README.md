# Algorithm for QR Decomposition
## Developed By:Mirtyunjay .S
## Register Number:212224040190
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```python
import numpy as np
np.set_printoptions(precision=8, suppress=True)

def qr_decomposition_gram_schmidt(A):
    A = np.array(A, dtype=float)
    m, n = A.shape
    Q = np.zeros((m, n))
    R = np.zeros((n, n))

    for j in range(n):
        v = A[:, j]
        for i in range(j):
            R[i, j] = np.dot(Q[:, i], A[:, j])
            v = v - R[i, j] * Q[:, i]
        R[j, j] = np.linalg.norm(v)
        Q[:, j] = v / R[j, j]
    return Q, R

# Input
A = eval(input())

Q, R = qr_decomposition_gram_schmidt(A)

print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)
```

## Output
<img width="1243" height="569" alt="Screenshot 2025-10-18 080939" src="https://github.com/user-attachments/assets/f5382f98-5d46-4c1a-b7a6-42b5dc160918" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
