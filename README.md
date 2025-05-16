# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start
2. Input number of variables n.
3. Create augmented matrix a[n][n+1] and solution array x[n].
4. Input all elements of the augmented matrix.
5. Forward Elimination (make lower triangle zero):
    For each row i:
    If diagonal element a[i][i] == 0, stop (division by zero).
    For each row below (j > i):
    Find ratio = a[j][i] / a[i][i]
    Subtract ratio * row i from row j
6. Back Substitution (solve values from bottom to top):
    Start with last variable.
    For each variable, subtract known values and divide to find unknown.
7. Print solution x[i] for each variable.
8. End


## Program:
```
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Jisha Bossne SJ
RegisterNumber: 212224230106
```
```
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range (n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```
## Output:

![Screenshot 2025-04-17 085529](https://github.com/user-attachments/assets/d1923424-4b52-443b-b74d-3944be74d638)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

