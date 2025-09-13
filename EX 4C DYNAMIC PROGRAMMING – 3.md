# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:20-07-2025
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.


## Algorithm

1. Read a string `s` from user input.
2. Compute the length `n` of the string `s`.
3. Create a reversed version of the string and store it in `str1`.
4. Initialize a 2D list `dp` of size (n+1) x (n+1) with all values set to zero.
5. Define the function `lps(s1, s2)` to compute the LCS between `s1` and `s2`.
6. Loop through i from 1 to n.
7. Inside that, loop through j from 1 to n.
8. If characters s1\[i-1] and s2\[j-1] are equal, set dp\[i]\[j] = 1 + dp\[i-1]\[j-1].
9. If not equal, set dp\[i]\[j] = max(dp\[i-1]\[j], dp\[i]\[j-1]).
10. Return dp\[n]\[n] which contains the length of the longest palindromic subsequence.

## Program:
```
Program to implement to find the length of the longest palindromic subsequence in it
Developed by: GANESH PRABHU J
Register Number: 212223220023
```
```PY
s=input()
n=len(s)
str1=s[::-1]
dp=[[0 for j in range(n+1)] for j in range(n+1)]
def lps(s1,s2):
    for i in range(1,n+1):
        for j in range(1,n+1):
            if s1[i-1]==s2[j-1]:
                dp[i][j]=1+dp[i-1][j-1]
            else:
                dp[i][j]=max(dp[i-1][j],dp[i][j-1])
    return dp[n][n]


print(f"The length of the LPS is {lps(s,str1)}")
```
## Output:

![image](https://github.com/user-attachments/assets/05ce9d50-6334-4cec-b9cb-46ab0fde081b)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
