# ctci-cheat_sheet
Making a "cheat sheet" from CTCI as I go through the book

## Arrays and Strings

## Linked Lists
Can be single or doubly linked

### Time complexities
Insert at beginning of list in O(1)

Get Nth element in O(n)

## Recursive Algorithms
All recursive algorithms take at least O(n) space, where n=depth of recursive call

## Stacks
A stack uses LIFO ordering.
One case where stacks are often useful is in certain recursive algorithms. Sometimes
you need to push temporary data onto a stack as you recurse, but then remove them as
you backtrack (for example, because the recursive check failed). A stack offers an
intuitive way to do this.

A stack can also be used to implement a recursive algorithm iteratively.

## Queue
A queue uses FIFO ordering.
One place where queues are often used is BFS(breadth first search) or in implementing
a cache.

## Trees
Be comfortable in implementing in-order, post-order and pre-order traversal.
In-order traversal means to "visit" the left branch, then the current node, and finally,
the right branch.
Pre-order traversal visits the current node before it's children.
Post-order traversal visits the current node after it's children. In post-order traversal
the root is always the last node visited.

### Trie (Prefix Tree)
A trie is a variant of an n-ary tree in which characters are stored at each node. Each
path down the tree may represent a word.
A * (star) node is often used to indicate complete words.

### BFS and DFS(Pseudocode)
```
def DFS(root: Node):
  if root == None:
    return
  visit(root)
  root.visited = true
  for node in root.adjacent:
    if node.visited == False:
      search(node)

def BFS(root: Node):
  queue = Queue()
  root.visited = true
  queue.append(root)

  while queue:
    node = queue.dequeue()
    visit(node)
    for n in root.adjacent:
      if node.visited == False:
        n.visited = True
        queue.append(n)

```
#### Bi-directional search
Bidirectional search is used to find the shortest path between a source and destination
node. It operates by essentially running two simultaneous breadth-first searches, one
from each node. When their searches collide, we have found a path.
