# BREADTH-FIRST-SEARCH

<h1>ExpNo 3 : Implement Breadth First Search Traversal of a Graph</h1>

<h3>Name: HARSHANA M V</h3>
<h3>Register Number: 212224240053</h3>

<hr>

<h3>Aim:</h3>
<p>To implement Breadth First Search (BFS) traversal of a graph using Python 3.</p>

<hr>

<h3>Theory:</h3>

<p>
Breadth-First Search (BFS) is a graph traversal algorithm that visits all the vertices of a graph level by level. It starts from a given source vertex and visits all its adjacent vertices before moving to the next level.
</p>

<p>
Unlike trees, graphs may contain cycles, so the same vertex may be encountered more than once. To avoid processing a vertex multiple times, the vertices are divided into two categories:
</p>

<ol>
<li>Visited</li>
<li>Not Visited</li>
</ol>

<p>
A Boolean visited array is used to keep track of the vertices that have already been visited. BFS uses a <strong>Queue</strong> data structure for traversal.
</p>

<p><strong>How does BFS work?</strong></p>

<p>
Starting from the source vertex, BFS visits all the nodes at the current level first and then moves to the nodes at the next level. The process continues until all reachable vertices have been visited.
</p>

<p>
To perform BFS, the starting vertex is inserted into the queue and marked as visited. The vertex at the front of the queue is then removed, and all its unvisited adjacent vertices are added to the queue and marked as visited.
</p>

<p><strong>Illustration:</strong></p>

<p>
Let us understand the working of the algorithm with the help of the following example.
</p>

<p><strong>Step 1:</strong> Initially, the queue and visited arrays are empty.</p>

<p>Queue and visited arrays are empty initially.</p>

<p><strong>Step 2:</strong> Push node 0 into the queue and mark it as visited.</p>

<p>Push node 0 into the queue and mark it visited.</p>

<p><strong>Step 3:</strong> Remove node 0 from the front of the queue. Visit its unvisited neighbours and push them into the queue.</p>

<p><strong>Step 4:</strong> Remove node 1 from the front of the queue. Visit its unvisited neighbours and push them into the queue.</p>

<p><strong>Step 5:</strong> Remove node 2 from the front of the queue. Visit its unvisited neighbours and push them into the queue.</p>

<p><strong>Step 6:</strong> Remove node 3 from the front of the queue and visit its unvisited neighbours. If all its neighbours have already been visited, move to the next node in the queue.</p>

<p><strong>Step 7:</strong> Remove node 4 from the front of the queue and visit its unvisited neighbours. If all its neighbours have already been visited, move to the next node in the queue.</p>

<p>
When the queue becomes empty, all reachable vertices have been visited and the BFS traversal is terminated.
</p>

<hr>

<h2>Algorithm:</h2>

<hr>

<ol>
<li>Construct a graph with vertices and edges.</li>
<li>Initialize a queue and a visited array.</li>
<li>Insert the starting node into the queue and mark it as visited.</li>
<li>Remove the node from the front of the queue.</li>
<li>Find all the adjacent vertices of the current node.</li>
<li>Check whether each adjacent vertex has been visited.</li>
<li>If a vertex has not been visited, mark it as visited and add it to the queue.</li>
<li>Repeat steps 4 to 7 until the queue becomes empty.</li>
<li>Display the BFS traversal path.</li>
</ol>

<hr>

<h3>Sample Input</h3>

<hr>

7 9<br>
A B<br>
A C<br>
A F<br>
C E<br>
C F<br>
C D<br>
D E<br>
D G<br>
G F<br>

<hr>

<h3>Sample Output</h3>

<hr>

['A', 'B', 'C', 'F', 'E', 'D', 'G']

<hr>

<h3>Sample Input</h3>

<hr>

5 6<br>
0 1<br>
0 2<br>
1 2<br>
1 3<br>
2 4<br>
3 4<br>

<hr>

<h3>Sample Output</h3>

<hr>

['0', '1', '2', '3', '4']

<hr>

<h3>PROGRAM:</h3>

<pre>
from collections import deque
from collections import defaultdict

'''
Input format:
V E
U V for each edge

Example:
7 9
A B
A C
A F
C E
C F
C D
D E
D G
G F
'''

def bfs(graph, start, visited, path):
    queue = deque()

    path.append(start)
    queue.append(start)
    visited[start] = True

    while queue:
        current_node = queue.popleft()

        # Visit all unvisited neighbours
        for neighbour in graph[current_node]:
            if not visited[neighbour]:
                visited[neighbour] = True
                queue.append(neighbour)
                path.append(neighbour)

    return path


print("Enter vertices and edges:")
graph = defaultdict(list)

vertices, edges = map(int, input().split())

print("Enter edges u v:")

for i in range(edges):
    u, v = input().split()

    # Add edges for an undirected graph
    graph[u].append(v)
    graph[v].append(u)

start = input("Enter start node: ")

path = []
visited = defaultdict(bool)

traversed_path = bfs(graph, start, visited, path)

print("BFS Traversal Path:", traversed_path)
</pre>

<hr>

<h3>OUTPUT:</h3>

<p>
<img width="416" height="181" alt="image" src="https://github.com/user-attachments/assets/bdca6e95-bb40-4c50-9cde-5dd316c31501" />

</p>

<hr>

<h3>Result:</h3>

<hr>

<p>
Thus, a graph was constructed and Breadth First Search (BFS) traversal was implemented successfully using Python 3.
</p>
