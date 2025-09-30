# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1. Input the number of variables n and augmented matrix a[n][n+1].
   
2. Perform forward elimination to transform the matrix into upper triangular form.

3. Apply back substitution to solve for unknowns starting from the last equation.

4. Print the solutions for all unknowns.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: AHAMADHSULAIMAN M
RegisterNumber: 212224230009
*/

import numpy as np
import sys

n = int(input())

a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][j] == 0.0:
        sys.exit("Divide by Zero detected")
    
    for j in range(i + 1, n):
        ratio = a[j][i]/a[i][i]
        for k in range(n + 1):
            a[j][k] = a[j][k] - ratio * a[i][k]

x[n - 1] = a[n-1][n] / a[n - 1][n - 1]
for i in range(n - 2, -1, -1):
    x[i] = a[i][n]
    for j in range(i + 1,n):
        x[i] = x[i] - a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
    
    
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')

```

## Output:

<img width="1251" height="617" alt="image" src="https://github.com/user-attachments/assets/4134c251-ce65-4a75-8b0f-0eda8f9c7e73" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

