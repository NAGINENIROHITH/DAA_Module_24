# EX 6A CHERRY PICK UP PROBLEM
## DATE:
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm
1. Initialize Parameters:

    Define the grid size with rows = len(grid) and cols = len(grid[0]).

    Use a memoization dictionary memo to store intermediate results of subproblems to avoid recomputation.

2. Define DP Function:

    Create a recursive function dp(r, c1, c2) where:

    r is the current row.

    c1 and c2 are the current column positions of two robots.

    If any robot is out of bounds or row exceeds the grid, return 0 (invalid path).

3. Collect Cherries:

    At each step, collect cherries from grid[r][c1] and grid[r][c2] (avoid double count if c1 == c2).

4. Explore All Moves:

    Try all 3 possible moves (-1, 0, 1) for both robots to go to the next row.

    Recursively calculate the max cherries collected from these 9 combinations.

    Add the current cherries to the result and store in memo.

5. Return Result:

    Start DP with dp(0, 0, cols - 1) representing robots starting at the top-left and top-right corners.

    Return the final result.   

## Program:
```
/*
To implement the program for Cherry pickup problem.
Developed by: 
Register Number:  
*/
```
```
class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        rows=len(grid)
        cols=len(grid[0])
        memo={}
        def dp(r,c1,c2):
            if r==rows or c1<0 or c1==cols or c2<0 or c2==cols:
                return 0
            if (r,c1,c2) in memo:
                return memo[(r,c1,c2)]
            cherries=grid[r][c1]+(grid[r][c2] if c1!=c2 else 0)
            maxcherries=0
            for dc1 in [-1,0,1]:
                for dc2 in [-1,0,1]:
                    maxcherries=max(maxcherries,dp(r+1,c1+dc1,c2+dc2))
            result=cherries+maxcherries
            memo[(r,c1,c2)]=result
            return result
        
        #############    Add your code here  ############### 

        return dp(0,0,cols-1)
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid)+3)
```
## Output:

![image](https://github.com/user-attachments/assets/6c7466ae-1c49-4085-8f52-42613c2cadc3)

## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
