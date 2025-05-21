# Ex. No: 18D - Travelling Salesman Problem (TSP)

## AIM:
To write a Python program to perform Topological Sorting of a Directed Acyclic Graph (DAG) using Depth First Search (DFS).

## ALGORITHM:

**Step 1**: Initialize adj[] to represent the graph as an adjacency list.

**Step 2**: Initialize visited[] to mark visited vertices (all set to 0 initially).

**Step 3**: Initialize departure[] to store the departure time of each vertex.

**Step 4**: Set a global counter time = 0.

**Step 5**: For each edge (u, v), add v to adj[u].

**Step 6**: Define a recursive DFS function:
    - Mark the current vertex v as visited.
    - For each unvisited neighbor u of v, call DFS(u). 
    - After all neighbors are visited, set departure[time] = v, then increment time.

**Step 7**: For each vertex v from 0 to V-1, if not visited, call DFS(v).

**Step 8**: Print the vertices in reverse order of departure[] for the topological sort.


## PYTHON PROGRAM

```
def addEdge(u, v):
	global adj
	adj[u].append(v)

def DFS(v):
	global visited, departure, time
	visited[v] = 1
	for i in adj[v]:
		if visited[i] == 0:
			DFS(i)
	departure[time] = v
	time += 1

def topologicalSort():
    for i in range(V):
        if (visited[i]==0):
            DFS(i)
    for i in range(V-1,-1,-1):
        print(departure[i],end=" ")

if __name__ == '__main__':
	
	V,time, adj, visited, departure = 6, 0, [[] for i in range(7)], [0 for i in range(7)],[-1 for i in range(7)]
	addEdge(5, 2)
	addEdge(5, 0)
	addEdge(4, 0)
	addEdge(4, 1)
	addEdge(2, 3)
	addEdge(3, 1)

	print("Topological Sort of the given graph is")
	topologicalSort()

```

## OUTPUT
![image](https://github.com/user-attachments/assets/f644eb9a-970d-4310-b93b-1b20da0c798b)


## RESULT
Thus the Python program to perform Topological Sorting of a Directed Acyclic Graph (DAG) using Depth First Search (DFS) is implemented and executed successfuly.


