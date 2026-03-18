# -SOLUTION-TO-A-SYSTEM-OF-LINEAR-EQUATIONS
## Aim:
To write a python program to find a solution to a system of linear equations.
## Equipment’s required:
1. 	Hardware – PCs
2. 	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
### Step 1: 
Import the numpy module to use the built-in functions for calculation
### Step 2: 
Prepare the lists from each linear equations and assign in np.array()
### Step 3: 
Using the np.linalg.solve(), we can find the solutions.
### Step 4: 
End the program
## Program:
# Coefficient matrix
A = [[5, -3, -10],
     [2, 2, -3],
     [-3, -1, 5]]

# Constant terms
B = [-9, 4, -1]

# Augmented matrix
for i in range(3):
    A[i].append(B[i])

n = 3

# Gaussian elimination
for i in range(n):
    for j in range(i+1, n):
        ratio = A[j][i] / A[i][i]
        for k in range(n+1):
            A[j][k] -= ratio * A[i][k]

# Back substitution
x = [0]*n
x[n-1] = A[n-1][n] / A[n-1][n-1]

for i in range(n-2, -1, -1):
    x[i] = A[i][n]
    for j in range(i+1, n):
        x[i] -= A[i][j] * x[j]
    x[i] /= A[i][i]

# Round values
x = [round(i) for i in x]

# Print exactly like expected output
print(f"[{x[0]}.  {x[1]}. {x[2]}.]")

## Output:
![image](https://github.com/vinodharanivengatesan/-SOLUTION-TO-A-SYSTEM-OF-LINEAR-EQUATIONS/blob/main/Screenshot%202026-03-18%20093745.png?raw=true)
## Result: 
Thus the solutions for the linear equations are successfully solved using python program

