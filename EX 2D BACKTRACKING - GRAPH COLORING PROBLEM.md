# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 29/04/2025
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1. Input: A graph adjacency matrix and the number of colors m.
2. Define isSafe(v, colour, c): Check if vertex v can be colored with color c without conflicts.


3. Define graphColourUtil(m, colour, v): Use backtracking to try coloring each vertex and move to the next.
4. Define graphColouring(m): Initialize the color array and call graphColourUtil to find a valid coloring.
5. Output: Print the assigned colors if a solution exists; otherwise, print "No solution exists".

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: Lavanya M
Register Number:  212222110021
*/

class Graph:
    def __init__(self,vertices):
        self.V=vertices
        self.graph=[[0 for row in range(vertices)] for column in range(vertices)]
        
    def isSafe(self,v,colour,c):
        for i in range(v):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
        
    def graphColourUtil(self,m,colour,v):
        if v==self.V:
            return True 
        for i in range(1,m+1):
            if self.isSafe(v,colour,i):
                colour[v]=i
                if self.graphColourUtil(m,colour,v+1):
                    return True
        return False
        
    def graphColouring(self,m):
        colour=[0]*self.V
        if not self.graphColourUtil(m,colour,0):
            print("No solution Exist")
            return False
        print("Solution exist and Following are the assigned colours:")
        
        for c in colour:
            print(c,end=' ')
        print()
        return True
        
        
        
```

## Output:
![image](https://github.com/user-attachments/assets/b5f82667-5c8b-40ad-a423-6a6339fc47c8)



## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
