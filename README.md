# Augmenting Paths

When we talked about the Ford-Fulkerson algorithm to find the maximum flow
through a graph, I mentioned the "find an augmenting path" function. You're
going to implement this function. Start with the template I provided in
`code.js`. Use an adjacency list data structure to represent the graph and node
names, not indices, to indicate start and end node. The function returns a list
of node names, starting with the start node and finishing with the end node. If
start and end node are the same, it should return a list containing only this
node. If there is no path, you must return an empty list.

Test your new function; I've provided some basic testing code in `code.test.js`.

To illustrate, here's an example graph:
![example graph](graph.png)

Here's the call for this graph:

```javascript
var graph = { foo: { boo: 7 }, boo: { foo: 3, bar: 2 }, bar: { boo: 4 } };
augmentingPath(graph, "foo", "bar");
```

The call would return `['foo', 'boo', 'bar']`.

Feel free to use other data structures, but you'll have to change the test code
accordingly.

## Runtime Analysis

What is the worst-case big $\Theta$ complexity of your implementation? Add your
answer, including your reasoning, to this markdown file.
I had help from ai to figure out the java script keywords for queues.

The worst case time complexity of this algorithm is big theta (m _ n) where m is the number of edges and n is the number of nodes in the graph. Its that way because the algorithm uses a breadth first search to traverse the graph, processing each edge once giving O(m), and for each edge, it constructs a new path by concatenating arrays, which in the worst case can take O(n) per edge. The cumulative cost of path construction leads to big theta (m _ n). the space complexity is big theta (n^2), as the algorithm maintatins a queue that stores paths, each of which contatin up to n nodes, and it uses a visited set to track up to n nodes. These bounds occur in the worst case, such as in a dense graph where m = O(n^2).

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."
