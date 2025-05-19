# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE: 29/04/2025
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Input: A list a[] and a target sum target.
2. Define SubsetSum(a, i, sum, target, n): Recursively check if a subset sum equals the target.
3. Base Cases: If i == n, check if sum == target; if sum > target, return False.
4. Recursion: Include or exclude each element and check the subset sum. 
5. Driver Code: Call SubsetSum and print the result along with whether a subset is found.

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: Lavanya M
Register Number:  212222110021
*/

def SubsetSum(a,i,sum,target,n):
    if i==n:
        return sum==target
    if sum>target:
        return False
    if sum==target:
        return True
    return SubsetSum(a,i+1,sum,target,n) or SubsetSum(a,i+1,sum+a[i],target,n)

a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")


```

## Output:

![image](https://github.com/user-attachments/assets/5caa026d-3eb3-441e-8a24-a95d1c4792b3)


## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
