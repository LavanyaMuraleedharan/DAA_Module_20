# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE: 29/04/2025
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1. Input: The size N of the chessboard.
2. Define isSafe(board, row, col): Check if placing a queen at (row, col) is safe (no attacks).
3. Define solveNQUtil(board, col): Try placing queens in each row of the current column recursively.


4. Backtracking: If placing a queen results in a solution, return True; otherwise, backtrack.
5. Driver Code: Initialize an empty board and call solveNQUtil to find and print the solution.

## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by:  Lavanya M
Register Number: 212222110021
*/

global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if(col>=N):
        return True
    for i in range(N):
        if isSafe(board,i,col):
            board[i][col]=1
            if(solveNQUtil(board,col+1)):
                return True
            board[i][col]=0
    return False
      
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()

```

## Output:

![image](https://github.com/user-attachments/assets/7bcd525c-025c-41df-8834-94efa8f7640e)


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
