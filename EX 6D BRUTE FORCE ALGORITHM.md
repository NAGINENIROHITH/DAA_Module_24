# EX 6D BRUTE FORCE ALGORITHM
## DATE:
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.

## Algorithm
1. Initialize Lengths:

    l = len(string) – length of the main string.

    ls = len(sub) – length of the substring.

2. Loop Over Possible Start Positions:

    For i from 0 to l - ls:

    Initialize j = 0.

3. Check for Match:

    While j < ls and string[i + j] == sub[j]:

    Increment j.

4. If Full Match Found:

    If j == ls, then the substring is found at index i.

    Print "Found at index", i.

5. Return -1:

    After checking all positions, return -1 (even though not used meaningfully here, included per function design).

## Program:
```
/*
To implement the program using brute force method of searching for the given substring in the main string.
Developed by: 
Register Number:  
*/
```
```
def match(string,sub):
    l = len(string)
    ls = len(sub)
    start = sub[0]

    ########### Add your code here #######
    for i in range(l-ls+1):
        j=0
        while j<ls and string[i+j]==sub[j]:
            j+=1
        if j==ls:
            print('Found at index',i)
    return -1

str1=input()
str2=input()

```
## Output:
![image](https://github.com/user-attachments/assets/1456de64-9be8-4b45-ad8a-a15cf9c1d9ec)

## Result:
Thus the above program was executed successfully for searching the substring at respective index.
