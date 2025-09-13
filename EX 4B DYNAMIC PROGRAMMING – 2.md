# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:20-07-2025
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..

## Algorithm

1. Read two strings X and Y from user input.
2. Compute lengths m and n of X and Y respectively.
3. Create a 2D list dp of size (m+1) x (n+1) initialized with zeros.
4. Initialize variables ma = 0 and end = 0 to track the maximum length and ending index of the common substring.
5. Loop over i from 1 to m.
6. Inside that, loop over j from 1 to n.
7. If X\[i-1] equals Y\[j-1], set dp\[i]\[j] = 1 + dp\[i-1]\[j-1].
8. If the new dp\[i]\[j] is greater than ma, update ma to dp\[i]\[j] and end to i.
9. After both loops, the longest common substring ends at index `end` in X and has length `ma`.
10. Return the substring X\[end - ma : end] as the longest common substring.

## Program:
```
Program to implement the longest common substring problem
Developed by: GANESH PRABHU J
Register Number: 212223220023
```
```PY
def LCSsunstr(X,Y,m,n):
    ma=0
    end=0
    dp=[[0 for j in range(n+1)] for i in range(m+1)]
    for i in range(1,m+1):
        for j in range(1,n+1):
            if X[i-1]==Y[j-1]:
                dp[i][j]=1+dp[i-1][j-1]
                if dp[i][j]>ma:
                    ma=dp[i][j]
                    end=i
    return X[end-ma:end]
        
X=input()
Y=input()
m=len(X)
n=len(Y)
print(f"The longest common substring is {LCSsunstr(X,Y,m,n)}")
```
## Output:

![image](https://github.com/user-attachments/assets/58d72ccf-be9c-485a-9d0e-51dbe8337c10)


## Result:
Thus the program was executed successfully for finding the longest common substring .
