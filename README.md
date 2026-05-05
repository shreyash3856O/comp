# Data Structures and Algorithms - MDM Experiments

This repository contains implementations of fundamental data structures and algorithms in C, covering 12 comprehensive experiments.

## Table of Contents

1. [Experiment 1: Array Insertion and Deletion](#experiment-1-array-insertion-and-deletion)
2. [Experiment 2: Recursive Programs](#experiment-2-recursive-programs)
3. [Experiment 3: Stack using Array](#experiment-3-stack-using-array)
4. [Experiment 4: Linear Queue using Array](#experiment-4-linear-queue-using-array)
5. [Experiment 5: Circular Queue using Array](#experiment-5-circular-queue-using-array)
6. [Experiment 6: Singly Linked List](#experiment-6-singly-linked-list)
7. [Experiment 7: Doubly Linked List](#experiment-7-doubly-linked-list)
8. [Experiment 8: Insertion Sort](#experiment-8-insertion-sort)
9. [Experiment 9: Selection Sort](#experiment-9-selection-sort)
10. [Experiment 10: Binary Search Tree](#experiment-10-binary-search-tree)
11. [Experiment 11: DFS and BFS](#experiment-11-dfs-and-bfs)
12. [Experiment 12: Binary Search](#experiment-12-binary-search)

---

## Experiment 1: Array Insertion and Deletion

**Objective:** Implementation of insertion and deletion operations at a specific position in an array using functions.

**Key Features:**
- Insert element at a specific position
- Delete element from a specific position
- Display array elements
- Boundary checks (array full, empty conditions)

**Functions:**
- `insert()` - Insert element at specified position
- `delete()` - Delete element from specified position
- `display()` - Print array elements

---

## Experiment 2: Recursive Programs

**Objective:** Implementation of recursive program to generate Fibonacci numbers.

**Key Features:**
- Recursive function to calculate nth Fibonacci number
- Base cases: F(0) = 0, F(1) = 1
- Recursive case: F(n) = F(n-1) + F(n-2)

**Functions:**
- `fibonacci(int n)` - Calculate nth Fibonacci number recursively

---

## Experiment 3: Stack using Array

**Objective:** Array implementation of Stack data structure.

**Key Features:**
- Push operation to add elements
- Pop operation to remove elements
- Display stack elements
- Overflow and underflow checks

**Functions:**
- `push()` - Add element to stack
- `pop()` - Remove and display top element
- `display()` - Print stack elements

**Operations:**
- Menu-driven interface for push, pop, display, and exit

---

## Experiment 4: Linear Queue using Array

**Objective:** Array implementation of Linear Queue data structure.

**Key Features:**
- Enqueue operation (insert at rear)
- Dequeue operation (remove from front)
- Peek operation (view front element)
- Display queue elements
- Fixed size queue

**Functions:**
- `enqueue(int n)` - Add element to queue
- `dequeue()` - Remove element from queue
- `peek()` - View front element
- `display()` - Print queue elements

---

## Experiment 5: Circular Queue using Array

**Objective:** Array implementation of Circular Queue data structure.

**Key Features:**
- Circular arrangement using modulo operator
- Efficient space utilization
- Enqueue and dequeue operations
- Peek operation
- Overflow and underflow handling

**Functions:**
- `enqueue(int n)` - Add element circularly
- `dequeue()` - Remove element from circular queue
- `peek()` - View front element
- `display()` - Print circular queue elements

---

## Experiment 6: Singly Linked List

**Objective:** Implementation of Singly Linked List with insertion and deletion operations.

**Key Features:**
- Dynamic memory allocation using malloc()
- Insertion at beginning, end, and specific position
- Deletion from beginning, end, and specific position
- Print linked list

**Functions:**
- `createNode(int data)` - Create new node
- `insertAtFirst()` - Insert at beginning
- `insertAtEnd()` - Insert at end
- `insertAtPosition()` - Insert at specific position
- `deleteFromFirst()` - Delete first node
- `deleteFromEnd()` - Delete last node
- `deleteAtPosition()` - Delete at specific position
- `print()` - Display linked list

---

## Experiment 7: Doubly Linked List

**Objective:** Implementation of Doubly Linked List with forward and backward traversal.

**Key Features:**
- Nodes with previous and next pointers
- Insertion at beginning, end, and specific position
- Deletion from beginning, end, and specific position
- Forward and reverse traversal
- Dynamic memory management

**Functions:**
- `createNode(int data)` - Create new node
- `insertAtBeginning()` - Insert at beginning
- `insertAtEnd()` - Insert at end
- `insertAtPosition()` - Insert at specific position
- `deleteAtBeginning()` - Delete from beginning
- `deleteAtEnd()` - Delete from end
- `deleteAtPosition()` - Delete at specific position
- `printListForward()` - Forward traversal
- `printListReverse()` - Backward traversal

---

## Experiment 8: Insertion Sort

**Objective:** Implementation of Insertion Sorting technique.

**Algorithm:**
- Divide array into sorted and unsorted portions
- Iterate through unsorted portion
- Insert each element into correct position in sorted portion
- Compare and shift elements as needed

**Time Complexity:**
- Best Case: O(n)
- Average Case: O(n²)
- Worst Case: O(n²)

---

## Experiment 9: Selection Sort

**Objective:** Implementation of Selection Sorting technique.

**Algorithm:**
- Find minimum element in unsorted portion
- Swap with first element of unsorted portion
- Move boundary between sorted and unsorted portions
- Repeat until array is sorted

**Time Complexity:**
- Best Case: O(n²)
- Average Case: O(n²)
- Worst Case: O(n²)

---

## Experiment 10: Binary Search Tree

**Objective:** Implementation of Binary Search Tree and its traversal methods.

**Key Features:**
- Tree node creation with left and right pointers
- Three traversal methods implemented

**Traversal Methods:**
- **Preorder (Root → Left → Right)** - Process root, then left subtree, then right subtree
- **Inorder (Left → Root → Right)** - Process left subtree, then root, then right subtree
- **Postorder (Left → Right → Root)** - Process left subtree, then right subtree, then root

**Functions:**
- `createNode(int value)` - Create tree node
- `preorder(struct Node* root)` - Preorder traversal
- `inorder(struct Node* root)` - Inorder traversal
- `postorder(struct Node* root)` - Postorder traversal

---

## Experiment 11: DFS and BFS

**Objective:** Implementation of Depth-First Search (DFS) and Breadth-First Search (BFS) graph traversal algorithms.

**Key Features:**
- Adjacency matrix representation of graph
- Queue implementation for BFS
- Recursive implementation for DFS

**Algorithms:**
- **DFS (Depth-First Search)** - Uses recursion, explores as far as possible along each branch
- **BFS (Breadth-First Search)** - Uses queue, explores all vertices at present depth before moving deeper

**Functions:**
- `enqueue()` - Add vertex to queue
- `dequeue()` - Remove vertex from queue
- `bfs(int start)` - Breadth-first search traversal
- `dfs(int v)` - Depth-first search traversal

---

## Experiment 12: Binary Search

**Objective:** Implementation of Binary Searching technique.

**Algorithm:**
- Array must be sorted
- Compare key with middle element
- If match found, return index
- If key < middle, search left half
- If key > middle, search right half
- Repeat until element found or search space exhausted

**Time Complexity:**
- Best Case: O(1)
- Average Case: O(log n)
- Worst Case: O(log n)

**Functions:**
- `binarySearch(int arr[], int n, int key)` - Binary search implementation

---

## Compilation and Execution

To compile any of the C programs:
```bash
gcc -o program_name program_name.c
```

To run the compiled program:
```bash
./program_name
```

---

## Author

These experiments are part of the Data Structures and Algorithms course.

---

## License

This repository is open-source and available for educational purposes.
