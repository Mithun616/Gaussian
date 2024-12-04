# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1: Accept the size of the augmented matrix, n.

Step 2:  Create an n×(n+1) augmented matrix a and a solution vector x.

Step 3:  Populate the augmented matrix a with user inputs.

Step 4:  Ensure no diagonal element in the matrix is zero; exit if a zero is detected to avoid division by zero.

Step 5: 
a. For each pivot row i, normalize the pivot row.
b. Subtract a scaled version of the pivot row from rows below to make the elements below the pivot zero.

Step 6:  Calculate the value of the last variable, x  n−1, using the last row.

Step 7: 
a. For each row from n−2 to 0, calculate the corresponding variable by subtracting contributions from previously solved variables.
b. Divide by the diagonal coefficient to find the solution for the current variable.

Step 8:  Divide each solution by its corresponding diagonal coefficient to ensure accuracy.

Step 9: Print the values of all variables 

Step 10: Display the results with formatting to two decimal places.End of the program

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by:  MITHUN KUMAR G
RegisterNumber: 24900789
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range (n):
    for j in range (n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1, n):
        ratio=a[j][i] / a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range (i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range (n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')

```

## Output:
![Screenshot 2024-12-04 214738](https://github.com/user-attachments/assets/50f79a65-07b0-4cc4-b320-cd82de0f88e1)
## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

