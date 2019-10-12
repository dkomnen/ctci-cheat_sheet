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
