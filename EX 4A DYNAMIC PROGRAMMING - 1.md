# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:20-07-2025
## AIM:
To find longest common subsequence using Dynamic Programming.

## Algorithm

1. Read two strings s1 and s2 from user input.
2. Create a 2D list dp of size (len(s1)+1) x (len(s2)+1) initialized with zeros.
3. Loop through s1 and s2 in reverse using indices i and j.
4. If s1\[i] equals s2\[j], set dp\[i]\[j] to 1 plus dp\[i+1]\[j+1].
5. If s1\[i] does not equal s2\[j], set dp\[i]\[j] to max(dp\[i+1]\[j], dp\[i]\[j+1]).
6. Continue filling the dp table until complete with dp\[0]\[0] holding the LCS length.
7. Initialize i = 0 and j = 0 to begin LCS reconstruction.
8. Loop while i is less than len(s1) and j is less than len(s2).
9. If s1\[i] equals s2\[j], print the character and increment both i and j; else move in the direction of higher dp value.
10. The printed characters form the final Longest Common Subsequence.


## Program:
```
Program to implement the longest common subsequence using Dynamic Programming
Developed by: GANESH PRABHU J
Register Number: 212223220023
```
```PY
s1=input()
s2=input()
def lcs(s1,s2):
    dp=[[0 for i in range(len(s2)+1)] for j in range(len(s1)+1)]
    for i in range(len(s1)-1,-1,-1):
        for j in range(len(s2)-1,-1,-1):
            if s1[i]==s2[j]:
                dp[i][j]=1+dp[i+1][j+1]
            else:
                dp[i][j]=max(dp[i+1][j],dp[i][j+1])
    return dp


def printlcs(a,b,dp):
    i=0
    j=0
    while not (i==len(s1) or j==len(s2)):
        if a[i]==b[j]:
            print(a[i],end="")
            i+=1
            j+=1
        elif dp[i][j+1]>dp[i+1][j]:
            j+=1
        else:
            i+=1
dp=lcs(s1,s2)
printlcs(s1,s2,dp)
```
## Output:

![image](https://github.com/user-attachments/assets/aa75903e-de60-4c54-8416-a9e9c19e23f5)

## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
