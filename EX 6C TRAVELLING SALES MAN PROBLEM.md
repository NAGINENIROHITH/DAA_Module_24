# EX 6C TRAVELLING SALES MAN PROBLEM
## DATE:
## AIM:
To Solve Travelling Sales man Problem for the following graph.

![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)



## Algorithm
1. Initialize Variables:

    vertex[]: List of cities except the starting city s.

    minpath: Set to a very large value to track the minimum cost.

2. Generate All Permutations:

    Generate all possible orders of visiting the remaining cities using permutations.

3. Calculate Cost for Each Permutation:

    For each permutation i:

    Set current cost cur = 0.

    Start from source k = s.

    For each city j in the permutation:

    Add graph[k][j] to cur.

    Update k = j (move to the next city).

    After the loop, add the cost to return from the last city back to the source (graph[k][s]).

    Update minpath with the minimum of current path and minpath.

4. Return minpath:

    The least cost path covering all cities and returning to the source.   

## Program:
```
/*
To implement the program for TSP.
Developed by: NAGINENI ROHITH
Register Number: 212222040105 
*/
```
```
from sys import maxsize
from itertools import permutations
V = 4
 

def travellingSalesmanProblem(graph, s):
    vetex=[]
    cur=0
    minpath=maxsize
    for i in range(V):
        if i!=s:
            vetex.append(i)
    # k=s
    nextper=permutations(vetex)
    for i in nextper:
        cur=0
        k=s
        for j in i:
            cur+=graph[k][j]
            k=j
        cur+=graph[k][s]
        minpath=min(minpath,cur)
    return minpath

if __name__ == "__main__":
 
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],[15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
```
## Output:
![image](https://github.com/user-attachments/assets/195874f6-731a-453d-9dc7-d6d5755d80c9)

## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
