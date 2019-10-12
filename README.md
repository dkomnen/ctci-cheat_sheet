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

### Types of Trees
#### Binary Tree
Any Tree in which each node has up to two children.
#### Binary Search Tree
A binary search tree is a binary tree which imposes the condition that, for each node,
its left descendents are less than or equal to the current node, which is less than the right
descendents.
#### Complete Binary Tree
Complete binary tree has every level of the tree fully filled, except maybe the last level.
To that extend that the last level is filled, it's filled left to right.
#### Full Binary Tree
A full binary tree is a binary tree in which every node has either zero or two children.
#### Perfect Binary Tree
Perfect binary trees are both full and complete.

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

## Object-Oriented Design
### How to Aproach
#### 1. Handle ambiguity
OOD questions are often intentionally vague in order to test whether you'll make assumptions
or if you'll ask clarifying questions.

When being asked an OOD question, you should inquire who is going to use it and how they are
going to use it. Depending on the question, you might even want to go through the 'six W': who,
what, where, when, how, why

#### 2. Define the core objects
Consider what the core objects are going to be in the given scenario, and define them.

#### 3. Analyze relationships
Think about the relationships between the defined objects. Do they inherit one another?
Are they many-to-many or one-to-many? Ask clarifying questions from your interviewer.

#### 4. Investigate actions
At this point you should have a basic outline of your OOD. What remains is to define the actions
the objects will take and how they relate to each other. You may find that you have forgotten
some objects, and need to update your design.

### Design patterns
The singleton and factory design pattern are widely used in interviews.

## Recursion and Dynamic Programming

### How to Aproach
Recursive solutions, by defition, are built off of solutions to subproblems.

There are many ways to divide a problem into subproblems. Three of the most common approaches
to develop an algorithm are bottom-up, top-down, and half-half.

#### Bottom-up approach
The bottom-up approach is the most intuitive. We start with knowing how to solve the problem for a simple
case, like a list with only one element. Then we figure out how to solve for two elements, then three
and so on. The key here is to think about how you can build the solution for one case off of the previous
case (or multiple previous cases).

#### Top-down approach
The top down approach can be more complex, since it's less concrete. But sometimes, it's the best way
to think about the problem.

In these problems, we think about how we can divide the problem for case N into subproblems.

#### Half-half approach
It's often effective to divide the data set in half.

For example, binary search works with a 'half-half' approach. When we look for an element in a sorted
array, we first figure out which half of the array contains the value. Then we recurse and search for
it in that half.

Merge sort tis also a 'half-half' approach. We sort each half of the array and then merge together the
sorted halves.

### Recursive vs Iterative solutions
Recursive algorithms can be very space inefficient. If your algorithm recurses to a depth of n, it
uses at least O(n) memory.

Before diving into recursive code, ask yourself how hard it would be to implement it iteratively,
and discuss the tradeoffs with your interviewer.

### Dynamic Programming
Dynamic programming is mostly just a matter of taking a recursive algorithm, and finding the
overlapping subproblems(that is, repeated calls). You then cache those results for future
recursive calls.
