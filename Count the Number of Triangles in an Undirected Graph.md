# Ex. No: 18E - Python program to generate a graph for a given fixed degree sequence.

## AIM:
To write a Python program that generates an undirected graph for a given fixed degree sequence without allowing self-loops or multiple edges, and to display its adjacency matrix.


## ALGORITHM:

**Step 1**: Start.

**Step 2** : Take input for the number of nodes (n) and read the degree sequence list degseq of size n.

**Step 3** : Initialize an n x n adjacency matrix with all zeros.

**Step 4** : Traverse all pairs (i, j) where i < j:

	-If both degseq[i] > 0 and degseq[j] > 0, then:

	-Add an edge between node i and node j by setting mat[i][j] = 1 and mat[j][i] = 1.

	-Decrement degseq[i] and degseq[j] by 1.

**Step 5** : After all possible edges are added (based on the degree sequence), print the adjacency matrix.

**Step 6** : End.



## PYTHON PROGRAM

# Python3 program to generate a graph
# for a given fixed degrees

# A function to print the adjacency matrix.
def printMat(degseq, n):
    mat=[[0]*n for i in range(n)]
    for i in range(n):
        for j in range(i+1,n):
            if (degseq[i]>0 and degseq[j]>0):
                degseq[i]-=1
                degseq[j]-=1
                mat[i][j]=1
                mat[j][i]=1
    print("      ", end ="")
    for i in range(n):
        print(" ", "(", i, ")", end ="")
    print()
    print()
    for i in range(n):
        print("  ", "(", i, ")", end = " ")
        for j in range(n):
            print("  ", mat[i][j], end = " ")
        print()

# Driver Code
degseq=[]
for i in range(0, 5):
    ele = int(input())
  
    degseq.append(ele)
#degseq =[v0,v1,v2,v3,v4]

n = len(degseq)
printMat(degseq, n)


```

## OUTPUT

![image](https://github.com/user-attachments/assets/7b1af859-6520-4f43-a73e-1b0dda97b3af)



## RESULT
Thus the  Python program to generate a graph for a given fixed degree sequence implemented and executed successfuly.
