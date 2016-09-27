## breadth-first search

**method:**
  * breadth-first search is an algorithm used to traverse trees/graphs
  * choose current node and mark as visited
  * add current node's unvisited edges to a queue
  * dequeue a node, set it as the current node, and mark as visited
  * repeat process

**time complexity:** O(V + E) -- where V is the number of vertices/edges and E is the number of edges
  * adding to a queue is done in O(1) time.  carrying out a O(1) operation N times gives you a O(N) time complexity.
  * in the worst case, each node and its edges will be added to the queue.
