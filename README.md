# RANK-OF-A-MATRIX
## Aim:
To write a python program to find the rank of a matrix
## Equipment’s required:
1. 	Hardware – PCs
2. 	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1. Convert the input matrix to a NumPy array with float data type.

2. Initialize rank = 0 and get the number of rows and columns of the matrix.

3. For each row i, if A[i, i] is zero, swap rows to place a non-zero element in the diagonal position.

4. If A[i, i] is non-zero, normalize row i by dividing it by A[i, i].

5. For each row j below row i, eliminate the element below the pivot by subtracting a multiple of row i from row j.

6. Count the number of non-zero rows in the resulting matrix and return the rank. 
## Program:
```
import numpy as np
def find_rank(matrix):
    A = np.array(matrix, dtype=float)
    rows, cols = A.shape
    rank = 0
    for i in range(rows):
        if A[i, i] == 0:
            for j in range(i+1, rows):
                if A[j, i] != 0:
                    A[[i, j]] = A[[j, i]]  
                    break
        if A[i, i] == 0:
            continue
        A[i] = A[i] / A[i, i]
        for j in range(i+1, rows):
            A[j] = A[j] - A[j, i] * A[i]
    for i in range(rows):
        if not np.allclose(A[i], 0): 
            rank += 1
    return rank

matrix = [[5, -3, -10], [2, 2, -3], [-3, -1, 5]]
rank = find_rank(matrix)
print(rank)
```
## Output:

![Screenshot 2025-03-27 195406](https://github.com/user-attachments/assets/58af726e-6751-4c33-a830-abf18942a65e)

![Screenshot 2025-03-27 195431](https://github.com/user-attachments/assets/e8e0d758-9798-48b3-aedb-2b5cef2fea29)

## Result:
Thus the rank for the given matrix is successfully solved by  using a python program.

