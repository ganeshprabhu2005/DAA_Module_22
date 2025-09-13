# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:20-07-2025
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm

1. Read two strings `str1` and `str2` from user input.
2. Define a recursive function `LD(s, t, m, n)` to compute edit distance between strings `s` and `t`.
3. Base case: if `m == 0`, return `n` since `s` is empty and needs `n` insertions.
4. Base case: if `n == 0`, return `m` since `t` is empty and needs `m` deletions.
5. If characters `s[m-1]` and `t[n-1]` are equal, return `LD(s, t, m-1, n-1)` with no operation needed.
6. If characters are different, consider all three operations:
7. Compute cost of deletion as `LD(s, t, m-1, n)`.
8. Compute cost of insertion as `LD(s, t, m, n-1)`.
9. Compute cost of substitution as `LD(s, t, m-1, n-1)`.
10. Return `1 + min(deletion, insertion, substitution)` as the minimum edit distance.

## Program:
```
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method
Developed by: GANESH PRABHU J
Register Number: 212223220023
```
```PY
def LD(s, t,m,n):
    res=0
    if m==0:
        return n
    if n==0:
        return m
    if s[m-1]==t[n-1]:
        return LD(s, t,m-1,n-1)
    else:
        return 1+min(LD(s, t,m-1,n),LD(s, t,m,n-1),LD(s, t,m-1,n-1))
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2,len(str1),len(str2)))


```
## Output:

![image](https://github.com/user-attachments/assets/c9c7fdaa-db03-410e-ae61-c7b5bda1c428)


## Result:
Thus the program was executed successfully for finding edit distance between two strings.
