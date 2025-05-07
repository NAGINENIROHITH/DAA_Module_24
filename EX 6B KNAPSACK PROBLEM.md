# EX 6B KNAPSACK PROBLEM
## DATE:
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.



## Algorithm
1. Input:

    W: Maximum capacity of the knapsack.

    val[]: Array of item values.

    wt[]: Array of item weights.

    n: Number of items.

2. Base Case:

    If n == 0 or W == 0, return 0 (no items or no capacity left).

3. Check Weight:

    If wt[n-1] > W, the current item cannot be included. Recursively call:

    knapSack(W, wt, val, n-1)

4. Include or Exclude:

  Else:

  Include the current item: val[n-1] + knapSack(W - wt[n-1], wt, val, n-1)

  Exclude the current item: knapSack(W, wt, val, n-1)

  Return the maximum of the two.

5. Output:

    The result is the maximum total value that can be carried in the knapsack without exceeding the weight W.  

## Program:
```
/*
To implement the program for 0/1 knapsack problem.
Developed by: NAGINENI ROHITH
Register Number:  212222040105
*/
```
```
def knapSack(W, wt, val, n):
    ########## Add your code here #########
    if n==0 or W==0:
        return 0
    if wt[n-1]>W:
        return knapSack(W,wt,val,n-1)
    else:
        inc=val[n-1]+knapSack(W-wt[n-1],wt,val,n-1)
        exc=knapSack(W,wt,val,n-1)
        return max(inc,exc)

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```
## Output:
![image](https://github.com/user-attachments/assets/ad3fb37e-a5a5-4e65-9caf-86b0d9169035)


## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
