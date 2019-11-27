## 133. Clone Graph
### Difficulty

 <font color=orange>Medium</font>

### Description

Given a reference of a node in a
**[connected](https://en.wikipedia.org/wiki/Connectivity_\(graph_theory\)#Connected_graph)**
undirected graph, return a [**deep
copy**](https://en.wikipedia.org/wiki/Object_copying#Deep_copy) (clone) of the
graph. Each node in the graph contains a val (`int`) and a list (`List[Node]`)
of its neighbors.



**Example:**

![](https://assets.leetcode.com/uploads/2019/11/04/133_clone_graph_question.png)
            Input: {"$id":"1","neighbors":[{"$id":"2","neighbors":[{"$ref":"1"},{"$id":"3","neighbors":[{"$ref":"2"},{"$id":"4","neighbors":[{"$ref":"3"},{"$ref":"1"}],"val":4}],"val":3}],"val":2},{"$ref":"4"}],"val":1}        ## Explanation:    Node 1's value is 1, and it has two neighbors: Node 2 and 4.    Node 2's value is 2, and it has two neighbors: Node 1 and 3.    Node 3's value is 3, and it has two neighbors: Node 2 and 4.    Node 4's value is 4, and it has two neighbors: Node 1 and 3.    



**Note:**

  1. The number of nodes will be between 1 and 100.
  2. The undirected graph is a [simple graph](https://en.wikipedia.org/wiki/Graph_\(discrete_mathematics\)#Simple_graph), which means no repeated edges and no self-loops in the graph.
  3. Since the graph is undirected, if node _p_  has node _q_  as neighbor, then node _q_  must have node _p_  as neighbor too.
  4. You must return the **copy of the given node** as a reference to the cloned graph.


### Related Topics

Depth-first Search, Breadth-first Search, Graph


### Link
[Clone Graph](https://leetcode.com/problems/clone-graph)
