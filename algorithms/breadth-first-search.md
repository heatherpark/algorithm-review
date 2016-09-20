## breadth-first search

**method:**
  * finds the shortest distance between two things
  * it finds the answers to the following:
    * _does a path between node A and node B exist?_
    * _what's the shortest path from node A to node B?_

**time complexity:** O(V + E) -- where V is the number of vertices/edges and E is the number of edges
  * adding to a queue is done in O(1) time.  carrying out a O(1) operation N times gives you a O(N) time complexity.
  * in the worst case, each node and its edges will be added to the queue.

#### implementation

```javascript
function breadthFirstSearch(node, target) {
  // create new queue to hold nodes to be searched
  var queue = new Queue;
  // use object to keep track of already searched nodes
  // prevents infinite loops when searching bi-directional relationships
  var searched = {};

  queue.enqueue(node);

  // while queue is not empty, search nodes for target node
  while (queue.size) {
    var currentNode = queue.dequeue();

    if (!searched.node) {
      if (node.value === target) {
        return true;
        // if target node has not yet been found
        // enqueue current node's edges
        // mark current node as searched
      } else {
        for (var edge in node.edges) {
          queue.enqueue(edge);
          searched[currentNode] = true;
        }
      }
    }
  }

  return false;
}
```
