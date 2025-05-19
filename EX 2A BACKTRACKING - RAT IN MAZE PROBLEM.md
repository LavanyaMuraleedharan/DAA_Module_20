# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 29/04/2025
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Input: A N x N maze with 1 for open paths and 0 for blocked paths.
2. Define isSafe(x, y): Check if the cell (x, y) is within bounds and open.
3. Define solveMaze(maze): Initialize a solution matrix and call solveMazeUtil starting from (0, 0).
4. Define solveMazeUtil(x, y): Use backtracking to explore possible paths (right or down) to reach the destination.
5. Print the solution matrix if a path is found; otherwise, print "Solution doesn't exist".

## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: Lavanya M
Register Number:  212222110021
*/

N = 4
 

def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
 

def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):
    if (x==N-1 and y==N-1):
        sol[x][y]=1
        return True
    elif (isSafe(maze,x,y)==True):
        sol[x][y]=1
        if(solveMazeUtil(maze,x+1,y,sol)==True):
            return True
        if(solveMazeUtil(maze,x,y+1,sol)==True):
            return True
        sol[x][y]=0
        return False
    return False
    
# Driver program to test above function
if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:

![image](https://github.com/user-attachments/assets/ca5baad5-82ec-4ad2-a490-70a0585ec44c)


## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
