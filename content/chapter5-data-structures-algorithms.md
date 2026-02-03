# Chapter 5: Data Structures & Algorithms

## Introduction

Data structures and algorithms form the foundation of computer science and software development. As an Assistant Director IT, understanding these concepts is crucial for making informed decisions about system design, performance optimization, and technology selection. This chapter covers essential data structures, algorithms, and complexity analysis.

## Linear Data Structures

### Arrays: Single-Dimensional, Multi-Dimensional

#### Single-Dimensional Arrays
- **Definition**: Contiguous memory locations storing elements of the same type
- **Access**: O(1) - direct access using index
- **Operations**:
  - Access: arr[i]
  - Insertion: O(n) - shifting elements
  - Deletion: O(n) - shifting elements
  - Search: O(n) for unsorted, O(log n) for sorted (binary search)
- **Advantages**: Fast access, cache-friendly
- **Disadvantages**: Fixed size, inefficient insertions/deletions

#### Multi-Dimensional Arrays
- **Definition**: Arrays with more than one dimension (2D, 3D, etc.)
- **Representation**: Array of arrays
- **Access**: O(1) - direct access using multiple indices
- **Memory Layout**:
  - Row-major: Elements stored row by row
  - Column-major: Elements stored column by column
- **Applications**: Matrices, game boards, image processing

### Linked Lists: Singly, Doubly, Circular

#### Singly Linked List
- **Structure**: Nodes with data and pointer to next node
- **Operations**:
  - Insertion at head: O(1)
  - Insertion at tail: O(n) without tail pointer
  - Deletion: O(n) to find element, O(1) to delete
  - Search: O(n)
- **Advantages**: Dynamic size, efficient insertions/deletions
- **Disadvantages**: No random access, extra memory for pointers

#### Doubly Linked List
- **Structure**: Nodes with data, pointer to next and previous nodes
- **Operations**:
  - Insertion/deletion: O(1) if node is known
  - Search: O(n)
- **Advantages**: Bidirectional traversal, efficient deletions
- **Disadvantages**: Extra memory for backward pointers

#### Circular Linked List
- **Structure**: Last node points back to first node
- **Types**:
  - Singly circular: Next of last node points to first
  - Doubly circular: Next of last points to first, prev of first points to last
- **Applications**: Round-robin scheduling, circular buffers

### Stacks: LIFO, Applications

#### Stack Properties
- **LIFO (Last In, First Out)**: Last element added is first removed
- **Operations**:
  - Push: Add element to top - O(1)
  - Pop: Remove element from top - O(1)
  - Peek/Top: View top element - O(1)
  - isEmpty: Check if stack is empty - O(1)

#### Implementation
- **Array-based**: Fixed size, efficient
- **Linked list-based**: Dynamic size, no overflow

#### Applications
- **Expression evaluation**: Infix to postfix conversion
- **Function calls**: Call stack management
- **Undo operations**: Text editors, browsers
- **Backtracking**: Maze solving, puzzle games
- **Syntax parsing**: Compiler design

### Queues: FIFO, Circular Queues, Priority Queues, Deque

#### Queue Properties
- **FIFO (First In, First Out)**: First element added is first removed
- **Operations**:
  - Enqueue: Add element to rear - O(1)
  - Dequeue: Remove element from front - O(1)
  - Front: View front element - O(1)
  - Rear: View rear element - O(1)

#### Circular Queue
- **Purpose**: Efficient use of array space
- **Concept**: Wrap around when reaching end of array
- **Operations**: Same complexity as regular queue
- **Advantages**: Prevents memory wastage

#### Priority Queue
- **Concept**: Elements with higher priority served first
- **Implementation**: Binary heap, Fibonacci heap
- **Operations**:
  - Insert: O(log n)
  - Extract Max/Min: O(log n)
  - Increase/Decrease Priority: O(log n)

#### Deque (Double-ended Queue)
- **Concept**: Elements can be added/removed from both ends
- **Operations**:
  - InsertFront/InsertRear: O(1)
  - DeleteFront/DeleteRear: O(1)
- **Applications**: Sliding window problems, palindrome checking

## Non-Linear Data Structures

### Trees: Binary Trees, BST, AVL, Red-Black, B-trees, B+ trees

#### Binary Trees
- **Definition**: Each node has at most two children (left, right)
- **Properties**:
  - Height: Maximum depth of tree
  - Complete binary tree: All levels filled except possibly last
  - Full binary tree: Each node has 0 or 2 children
  - Balanced: Heights of subtrees differ by at most 1

#### Binary Search Tree (BST)
- **Property**: Left subtree < root < right subtree
- **Operations**:
  - Search: O(h) where h is height
  - Insert: O(h)
  - Delete: O(h)
- **Balanced vs Unbalanced**: O(log n) vs O(n) performance

#### AVL Trees
- **Property**: Self-balancing BST with height difference ≤ 1
- **Balancing**: Rotations (left, right, left-right, right-left)
- **Operations**: O(log n) guaranteed for all operations
- **Use Cases**: When guaranteed logarithmic performance is needed

#### Red-Black Trees
- **Properties**:
  - Nodes are red or black
  - Root is black
  - No two red nodes adjacent
  - All paths have same number of black nodes
- **Operations**: O(log n) for all operations
- **Advantages**: Less rotation than AVL during insertion/deletion

#### B-trees
- **Purpose**: Optimized for systems with large blocks of data
- **Properties**:
  - All leaves at same level
  - Each node contains multiple keys
  - Designed for disk storage
- **Applications**: Database indexes, file systems

#### B+ trees
- **Variation**: All data in leaves, internal nodes for navigation
- **Advantages**: Sequential access, range queries
- **Applications**: Database systems, file systems

### Tree Traversals: Inorder, Preorder, Postorder, Level-Order

#### Depth-First Traversals
- **Inorder (Left, Root, Right)**: For BST gives sorted order
- **Preorder (Root, Left, Right)**: For copying tree structure
- **Postorder (Left, Right, Root)**: For deleting tree, expression evaluation

#### Breadth-First Traversal
- **Level-order**: Visit nodes level by level
- **Implementation**: Using queue
- **Applications**: Finding shortest path in unweighted tree

### Heaps: Min-Heap, Max-Heap, Heap Operations

#### Heap Properties
- **Complete binary tree**: All levels filled except possibly last
- **Heap property**: Parent-child relationship maintained
  - Min-heap: Parent ≤ children
  - Max-heap: Parent ≥ children

#### Heap Operations
- **Insert**: Add to end, bubble up - O(log n)
- **Extract Min/Max**: Remove root, replace with last element, bubble down - O(log n)
- **Build Heap**: Convert array to heap - O(n)

#### Applications
- **Priority queues**: Task scheduling, event simulation
- **Heap sort**: O(n log n) sorting algorithm
- **Selection algorithms**: Finding kth largest/smallest

### Graphs: Directed, Undirected, Weighted

#### Graph Representation
- **Directed Graph**: Edges have direction (arcs)
- **Undirected Graph**: Edges have no direction
- **Weighted Graph**: Edges have weights/costs
- **Complete Graph**: All vertices connected to each other

#### Graph Terminology
- **Vertex/Node**: Fundamental unit
- **Edge**: Connection between vertices
- **Degree**: Number of edges incident to vertex
- **Path**: Sequence of vertices connected by edges
- **Cycle**: Path that starts and ends at same vertex
- **Connected**: Path exists between any two vertices

### Graph Representations: Adjacency Matrix, Adjacency List

#### Adjacency Matrix
- **Structure**: 2D array where matrix[i][j] represents edge
- **Space**: O(V²) where V is number of vertices
- **Operations**:
  - Check if edge exists: O(1)
  - Find all neighbors: O(V)
  - Add/remove edge: O(1)

#### Adjacency List
- **Structure**: Array of lists, each vertex has list of neighbors
- **Space**: O(V + E) where E is number of edges
- **Operations**:
  - Check if edge exists: O(degree of vertex)
  - Find all neighbors: O(degree of vertex)
  - Add/remove edge: O(degree of vertex)

#### Comparison
- **Sparse graphs**: Adjacency list more efficient
- **Dense graphs**: Adjacency matrix may be better
- **Memory constraints**: Adjacency list uses less space

### Graph Traversals: BFS, DFS

#### Breadth-First Search (BFS)
- **Approach**: Explore all neighbors before moving to next level
- **Implementation**: Using queue
- **Applications**:
  - Shortest path in unweighted graph
  - Level-order traversal
  - Connected components
- **Time Complexity**: O(V + E)

#### Depth-First Search (DFS)
- **Approach**: Explore as far as possible along each branch
- **Implementation**: Using stack (iterative) or recursion
- **Applications**:
  - Topological sorting
  - Detecting cycles
  - Finding strongly connected components
- **Time Complexity**: O(V + E)

## Hash-Based Structures

### Hash Tables and Hash Functions

#### Hash Table Concept
- **Purpose**: Map keys to values for fast access
- **Structure**: Array of buckets with hash function
- **Operations**: O(1) average case for search, insert, delete

#### Hash Function Properties
- **Deterministic**: Same input always produces same output
- **Uniform**: Distributes keys evenly across buckets
- **Efficient**: Computes quickly
- **Low collision**: Different inputs rarely map to same output

#### Common Hash Functions
- **Division method**: h(k) = k mod m
- **Multiplication method**: h(k) = floor(m * (kA mod 1))
- **Universal hashing**: Randomly chosen from family of hash functions

### Collision Resolution: Chaining, Open Addressing

#### Chaining
- **Concept**: Each bucket contains linked list of elements
- **Operations**:
  - Insert: Add to front of list - O(1)
  - Search/Delete: Traverse list - O(n/m) average
- **Advantages**: Simple, handles arbitrary number of collisions
- **Disadvantages**: Extra memory for pointers

#### Open Addressing
- **Concept**: All elements stored in hash table array
- **Methods**:
  - **Linear probing**: Check next slot (h(k) + i) mod m
  - **Quadratic probing**: Check (h(k) + c₁i + c₂i²) mod m
  - **Double hashing**: Check (h₁(k) + i*h₂(k)) mod m

#### Load Factor
- **Definition**: α = n/m where n is elements, m is slots
- **Impact**: Affects performance of hash table
- **Rehashing**: Resize table when load factor exceeds threshold

## Algorithms

### Sorting: Bubble, Selection, Insertion, Merge, Quick, Heap, Counting, Radix

#### Bubble Sort
- **Concept**: Repeatedly swap adjacent elements if out of order
- **Time Complexity**: O(n²)
- **Space Complexity**: O(1)
- **Stable**: Yes
- **Use Case**: Educational purposes, small datasets

#### Selection Sort
- **Concept**: Find minimum element and place at beginning
- **Time Complexity**: O(n²)
- **Space Complexity**: O(1)
- **Stable**: No
- **Use Case**: Small datasets, minimal memory writes

#### Insertion Sort
- **Concept**: Build sorted array one element at a time
- **Time Complexity**: O(n²) worst case, O(n) best case
- **Space Complexity**: O(1)
- **Stable**: Yes
- **Use Case**: Small datasets, nearly sorted data

#### Merge Sort
- **Concept**: Divide and conquer, merge sorted halves
- **Time Complexity**: O(n log n)
- **Space Complexity**: O(n)
- **Stable**: Yes
- **Use Case**: Large datasets, guaranteed performance

#### Quick Sort
- **Concept**: Divide and conquer with pivot element
- **Time Complexity**: O(n log n) average, O(n²) worst
- **Space Complexity**: O(log n)
- **Stable**: No
- **Use Case**: General-purpose sorting, good average performance

#### Heap Sort
- **Concept**: Build heap and repeatedly extract max/min
- **Time Complexity**: O(n log n)
- **Space Complexity**: O(1)
- **Stable**: No
- **Use Case**: Guaranteed O(n log n), in-place sorting

#### Counting Sort
- **Concept**: Count occurrences of each element
- **Time Complexity**: O(n + k) where k is range
- **Space Complexity**: O(k)
- **Stable**: Yes
- **Use Case**: Small integer range, limited range

#### Radix Sort
- **Concept**: Sort by individual digits/place values
- **Time Complexity**: O(d*(n + k)) where d is digits, k is base
- **Space Complexity**: O(n + k)
- **Stable**: Yes
- **Use Case**: Integer sorting, fixed-length keys

### Searching: Linear, Binary, Interpolation

#### Linear Search
- **Concept**: Check each element sequentially
- **Time Complexity**: O(n)
- **Space Complexity**: O(1)
- **Use Case**: Unsorted data, small datasets

#### Binary Search
- **Concept**: Divide and conquer on sorted array
- **Time Complexity**: O(log n)
- **Space Complexity**: O(1) iterative, O(log n) recursive
- **Prerequisite**: Sorted array
- **Use Case**: Sorted data, frequent searches

#### Interpolation Search
- **Concept**: Improved binary search for uniformly distributed data
- **Time Complexity**: O(log log n) average, O(n) worst
- **Space Complexity**: O(1)
- **Prerequisite**: Sorted and uniformly distributed data
- **Use Case**: Large, uniformly distributed datasets

### Shortest Path: Dijkstra's, Bellman-Ford

#### Dijkstra's Algorithm
- **Purpose**: Find shortest paths from single source to all vertices
- **Constraint**: No negative weight edges
- **Time Complexity**: O((V + E) log V) with binary heap
- **Algorithm**:
  1. Initialize distances, set source distance to 0
  2. Use priority queue to process closest unvisited vertex
  3. Update distances of adjacent vertices
  4. Repeat until all vertices processed

#### Bellman-Ford Algorithm
- **Purpose**: Find shortest paths from single source to all vertices
- **Advantage**: Handles negative weight edges
- **Detection**: Can detect negative weight cycles
- **Time Complexity**: O(VE)
- **Algorithm**:
  1. Initialize distances
  2. Relax all edges V-1 times
  3. Check for negative weight cycles

### Minimum Spanning Tree: Prim's, Kruskal's

#### Minimum Spanning Tree (MST)
- **Definition**: Subset of edges that connects all vertices with minimum total weight
- **Properties**: Forms tree, connects all vertices, minimum total weight

#### Prim's Algorithm
- **Approach**: Grow tree one vertex at a time
- **Time Complexity**: O((V + E) log V) with binary heap
- **Algorithm**:
  1. Start with arbitrary vertex
  2. Add minimum weight edge connecting tree to non-tree vertex
  3. Repeat until all vertices included

#### Kruskal's Algorithm
- **Approach**: Add minimum weight edges without creating cycles
- **Time Complexity**: O(E log E)
- **Algorithm**:
  1. Sort all edges by weight
  2. Use disjoint-set data structure to detect cycles
  3. Add edges in ascending order if no cycle formed

### Dynamic Programming Concepts

#### Dynamic Programming Approach
- **Optimal Substructure**: Optimal solution contains optimal solutions to subproblems
- **Overlapping Subproblems**: Recursive algorithm revisits same subproblems
- **Memoization**: Store results of expensive function calls
- **Tabulation**: Build solution bottom-up

#### Common DP Problems
- **Fibonacci sequence**: F(n) = F(n-1) + F(n-2)
- **Longest Common Subsequence**: Find common subsequence of two sequences
- **Knapsack problem**: Maximize value with weight constraint
- **Matrix chain multiplication**: Optimal way to multiply matrices

### Greedy Algorithms

#### Greedy Approach
- **Strategy**: Make locally optimal choice at each step
- **Requirements**: Greedy choice property, optimal substructure
- **Advantages**: Simple, efficient
- **Disadvantages**: Doesn't always yield optimal solution

#### Examples
- **Activity selection**: Select maximum number of non-overlapping activities
- **Fractional knapsack**: Take items with highest value-to-weight ratio
- **Huffman coding**: Optimal prefix-free binary code
- **Prim's and Kruskal's**: MST algorithms are greedy

### Divide and Conquer

#### Divide and Conquer Approach
- **Divide**: Break problem into smaller subproblems
- **Conquer**: Solve subproblems recursively
- **Combine**: Combine solutions to subproblems

#### Examples
- **Merge sort**: Divide array, sort halves, merge
- **Binary search**: Divide array, search in appropriate half
- **Quick sort**: Partition array, sort partitions
- **Strassen's matrix multiplication**: Divide matrices into quadrants

### Backtracking

#### Backtracking Approach
- **Strategy**: Build solution incrementally, abandon if it doesn't lead to valid solution
- **Applications**: Constraint satisfaction problems, combinatorial problems
- **Examples**:
  - N-Queens problem: Place queens without attacking each other
  - Sudoku solver: Fill grid following rules
  - Graph coloring: Color vertices with minimum colors
  - Hamiltonian path: Find path visiting each vertex once

## Complexity Analysis

### Time Complexity: Big O, Big Theta, Big Omega

#### Big O Notation (Upper Bound)
- **Definition**: f(n) = O(g(n)) if f(n) ≤ c*g(n) for large n
- **Purpose**: Describe worst-case scenario
- **Examples**:
  - O(1): Constant time
  - O(log n): Logarithmic time
  - O(n): Linear time
  - O(n log n): Linearithmic time
  - O(n²): Quadratic time
  - O(2ⁿ): Exponential time

#### Big Omega Notation (Lower Bound)
- **Definition**: f(n) = Ω(g(n)) if f(n) ≥ c*g(n) for large n
- **Purpose**: Describe best-case scenario

#### Big Theta Notation (Tight Bound)
- **Definition**: f(n) = Θ(g(n)) if f(n) = O(g(n)) and f(n) = Ω(g(n))
- **Purpose**: Describe average-case scenario with tight bounds

### Space Complexity Analysis

#### Space Complexity
- **Definition**: Amount of memory required by algorithm
- **Components**:
  - Input space: Memory for input data
  - Auxiliary space: Extra memory used by algorithm
  - Output space: Memory for output data
- **Analysis**: Focus on auxiliary space

#### Examples
- **Iterative algorithms**: Usually O(1) auxiliary space
- **Recursive algorithms**: O(recursion depth) for call stack
- **Dynamic programming**: Often O(n) or O(n²) for memoization table

### Best, Average, Worst Case Scenarios

#### Best Case
- **Definition**: Minimum time/space required
- **Example**: Linear search finds element at first position - O(1)

#### Average Case
- **Definition**: Expected time/space with random input
- **Example**: Linear search - O(n/2) ≈ O(n)

#### Worst Case
- **Definition**: Maximum time/space required
- **Example**: Linear search doesn't find element - O(n)

#### Importance
- **Worst case**: Guarantee performance bounds
- **Average case**: Real-world performance expectation
- **Best case**: Theoretical lower bound

## Summary

This chapter covered essential data structures and algorithms that form the foundation of computer science. Understanding these concepts is crucial for making informed decisions about system design, performance optimization, and technology selection. The next chapter will focus on Object-Oriented Programming concepts.

## Key Takeaways

1. Different data structures offer trade-offs between access, insertion, deletion, and space complexity
2. Trees provide hierarchical organization with efficient search capabilities
3. Hash tables offer constant-time average case operations
4. Graph algorithms solve complex network and relationship problems
5. Algorithm design paradigms (divide-and-conquer, greedy, dynamic programming) provide systematic approaches to problem-solving
6. Complexity analysis helps predict performance characteristics
7. Understanding time-space trade-offs is crucial for system design

## Practice Questions

1. What is the time complexity of inserting an element into a balanced binary search tree?
2. Explain the difference between a stack and a queue.
3. What is the main advantage of using a hash table over a binary search tree?
4. Name three divide-and-conquer algorithms.
5. What is the difference between Big O and Big Theta notation?

## Answers

1. O(log n) - In a balanced BST, insertion requires finding the correct position which takes logarithmic time.
2. A stack follows LIFO (Last In, First Out) principle, while a queue follows FIFO (First In, First Out) principle.
3. Hash tables provide O(1) average case operations, while BSTs provide O(log n) operations in balanced trees.
4. Merge sort, Quick sort, and Binary search are three divide-and-conquer algorithms.
5. Big O describes an upper bound (worst case), while Big Theta describes a tight bound (both upper and lower bounds).