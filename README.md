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

**Implementation of Insertion and Deletion in a Specific Position in an Array Using Functions.**

```c
#include <stdio.h>
#define MAX 100

int a[MAX], n; // Global variables

// Function to insert element
void insert()
{
    int pos, value;
    printf("Enter position to insert: ");
    scanf("%d", &pos);
    printf("Enter value to insert: ");
    scanf("%d", &value);

    if (n >= MAX)
    {
        printf("Array is full!\n");
        return;
    }

    for (int i = n; i >= pos; i--)
    {
        a[i] = a[i - 1];
    }

    a[pos - 1] = value;
    n++;
    printf("Element inserted successfully.\n");
}

// Function to delete element
void delete()
{
    int pos;
    printf("Enter position to delete: ");
    scanf("%d", &pos);

    if (n == 0)
    {
        printf("Array is empty!\n");
        return;
    }

    for (int i = pos - 1; i < n - 1; i++)
    {
        a[i] = a[i + 1];
    }

    n--;
    printf("Element deleted successfully.\n");
}

// Function to display array
void display()
{
    printf("Array elements are: ");
    for (int i = 0; i < n; i++)
    {
        printf("%d ", a[i]);  // FIXED
    }
    printf("\n");
}

int main()
{
    int choice;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter elements:\n");
    for (int i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);
    }

    insert();
    display();
    delete();
    display();

    return 0;  // FIXED POSITION
}
```

---

## Experiment 2: Recursive Programs

**Implementation of recursive program**

```c
#include <stdio.h>
int fibonacci(int n) {
if (n == 0)
return 0;
else if (n == 1)
return 1;
else
return fibonacci(n-1) + fibonacci(n-2);
}
int main() {
int n, i;
printf("Enter number of terms:");
scanf("%d", &n);
for(i = 0; i < n; i++)
printf("%d ", fibonacci(i));
return 0;
}
```

---

## Experiment 3: Array Implementation of Stack

```c
#include<stdio.h>

int stack[100], choice, n, Top, x, i;

void push(void);
void pop(void);
void display(void);

int main()
{
    Top = -1;

    printf("\nEnter the size of STACK: ");
    scanf("%d",&n);

    printf("\n\tSTACK OPERATIONS USING ARRAY");
    printf("\n\t--------------------------------");
    printf("\n\t1.PUSH\n\t2.POP\n\t3.DISPLAY\n\t4.EXIT");

    do
    {
        printf("\nEnter the Choice: ");
        scanf("%d",&choice);

        switch(choice)
        {
            case 1:
                push();
                break;

            case 2:
                pop();
                break;

            case 3:
                display();
                break;

            case 4:
                printf("\n\tEXIT POINT");
                break;

            default:
                printf("\n\tPlease Enter a Valid Choice(1/2/3/4)");
        }

    } while(choice != 4);

    return 0;
}

void push()
{
    if(Top >= n-1)
    {
        printf("\n\tSTACK is overflow");
    }
    else
    {
        printf("Enter a value to be pushed: ");
        scanf("%d",&x);
        Top++;
        stack[Top] = x;
    }
}

void pop()
{
    if(Top <= -1)
    {
        printf("\n\tStack is underflow");
    }
    else
    {
        printf("\n\tThe popped element is %d", stack[Top]);
        Top--;
    }
}

void display()
{
    if(Top >= 0)
    {
        printf("\nThe elements in STACK are:\n");
        for(i = Top; i >= 0; i--)
        {
            printf("%d\n", stack[i]);
        }
    }
    else
    {
        printf("\nThe STACK is empty");
    }
}
```

---

## Experiment 4: Array Implementation of Linear Queue

```c
#include<stdio.h>

#define Max 5

int queue[Max];
int front = -1, rear = -1;

void enqueue(int);
void dequeue();
void peek();
void display();

int main()
{
    int option, n;

    printf("*********Main Menu*************");
    printf("\n1.Enqueue\n2.Dequeue\n3.Peek\n4.Display\n5.Exit");

    do
    {
        printf("\nSelect the Option: ");
        scanf("%d", &option);

        switch(option)
        {
            case 1:
                printf("Enter the value to be inserted in queue: ");
                scanf("%d", &n);
                enqueue(n);
                break;

            case 2:
                dequeue();
                break;

            case 3:
                peek();
                break;

            case 4:
                display();
                break;

            case 5:
                printf("EXIT");
                break;

            default:
                printf("Invalid Option Selected");
        }

    } while(option != 5);

    return 0;
}

void enqueue(int n)
{
    if(rear == Max - 1)
    {
        printf("Overflow");
    }
    else if(front == -1 && rear == -1)
    {
        front = rear = 0;
        queue[rear] = n;
    }
    else
    {
        rear++;
        queue[rear] = n;
    }
}

void dequeue()
{
    if(front == -1 || front > rear)
    {
        printf("Underflow");
    }
    else
    {
        printf("Deleted element: %d", queue[front]);
        front++;
    }
}

void peek()
{
    if(front == -1 || front > rear)
    {
        printf("Queue is Empty");
    }
    else
    {
        printf("Front element: %d", queue[front]);
    }
}

void display()
{
    if(front == -1 || front > rear)
    {
        printf("Queue is Empty");
    }
    else
    {
        printf("The Elements in Queue are: ");
        for(int i = front; i <= rear; i++)
        {
            printf("%d\t", queue[i]);
        }
    }
}
```

---

## Experiment 5: Array Implementation of Circular Queue

```c
#include<stdio.h>
#define N 5
int queue[N];
int front=-1,rear=-1;
void enqueue(int);
void dequeue();
int peek();
void display();
int main()
{
int option,n,x;
printf("*********Main Menu*************");
printf("\n1.Enqueue\n2.Dequeue\n3.Peek\n4.Display\n5.Exit");
do
{
printf("\nSelect the Option:");
scanf("%d",&option);
switch(option)
{
case 1:
{
printf("Enter the value to be inserted on queue:");
scanf("%d",&n);
enqueue(n);
break;
}
case 2:
{
dequeue();
break;
}
case 3:
{
x=peek();
printf("The Element in front is:%d",x);
break;
}
case 4:
{
display();
break;
}
case 5:
{
printf("EXIT");
break;
}
default:
{
printf("Invalid Option Selected");
}
}
}
while(option!=5);
return 0;
}
void enqueue(int n)
{
if(front==-1 && rear==-1)
{
front=rear=0;
queue[rear]=n;
}
else if((rear+1)%N==front)
{
printf("Overflow");
}
else{
rear=(rear+1)%N;
queue[rear]=n;
}
}
void dequeue()
{
if(front== -1 && rear == -1)
{
printf("Underflow");
}
else if(front==rear)
{
front=rear=-1;
}
else
{front=(front+1)%N;}
}
int peek()
{
if(front == -1 && rear== -1)
{
printf("Queue is Empty");
}
else
{
return queue[front];
}
}
void display()
{
if(front==-1 && rear==-1)
{
printf("Queue is Empty");
}
else
{
int i=front;
printf("The Elements in Queue is:");
while(i!=rear)
{
printf("%d\t",queue[i]);
i=(i+1)%N;
}
printf("%d",queue[rear]);
}
}
```

---

## Experiment 6: Implement Singly Linked List

```c
// C Program for Implementation of Singly Linked List
#include <stdio.h>
#include <stdlib.h>
// Define the Node structure
struct Node {
int data;
struct Node* next;
};
// Function to create a new node
struct Node* createNode(int data) {
struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
newNode->data = data;
newNode->next = NULL;
return newNode;
}
// Function to insert a new element at the beginning of the singly linked list
void insertAtFirst(struct Node** head, int data) {
struct Node* newNode = createNode(data);
newNode->next = *head;
*head = newNode;
}
// Function to insert a new element at the end of the singly linked list
void insertAtEnd(struct Node** head, int data) {
struct Node* newNode = createNode(data);
if (*head == NULL) {
*head = newNode;
return;
}
struct Node* temp = *head;
while (temp->next != NULL) {
temp = temp->next;
}
temp->next = newNode;
}
// Function to insert a new element at a specific position in the singly linked list
void insertAtPosition(struct Node** head, int data, int position) {
struct Node* newNode = createNode(data);
if (position == 0) {
insertAtFirst(head,data);
return;
}
struct Node* temp = *head;
for (int i = 0; temp != NULL && i < position - 1; i++) {
temp = temp->next;
}
if (temp == NULL) {
printf("Position out of range\n");
free(newNode);
return;
}
newNode->next = temp->next;
temp->next = newNode;
}
// Function to delete the first node of the singly linked list
void deleteFromFirst(struct Node** head) {
if (*head == NULL) {
printf("List is empty\n");
return;
}
struct Node* temp = *head;
*head = temp->next;
free(temp);
}
// Function to delete the last node of the singly linked list
void deleteFromEnd(struct Node** head) {
if (*head == NULL) {
printf("List is empty\n");
return;
}
struct Node* temp = *head;
if (temp->next == NULL) {
free(temp);
*head = NULL;
return;
}
while (temp->next->next != NULL) {
temp = temp->next;
}
free(temp->next);
temp->next = NULL;
}
// Function to delete a node at a specific position in the singly linked list
void deleteAtPosition(struct Node** head, int position) {
if (*head == NULL) {
printf("List is empty\n");
return;
}
struct Node* temp = *head;
if (position == 0) {
deleteFromFirst(head);
return;
}
for (int i = 0; temp != NULL && i < position - 1; i++) {
temp = temp->next;
}
if (temp == NULL || temp->next == NULL) {
printf("Position out of range\n");
return;
}
struct Node* next = temp->next->next;
free(temp->next);
temp->next = next;
}
// Function to print the LinkedList
void print(struct Node* head) {
struct Node* temp = head;
while (temp != NULL) {
printf("%d -> ", temp->data);
temp = temp->next;
}
printf("NULL\n");
}
// Driver Code
int main() {
struct Node* head = NULL;
insertAtFirst(&head, 10);
printf("Linked list after inserting the node:10 at the beginning \n");
print(head);
printf("Linked list after inserting the node:20 at the end \n");
insertAtEnd(&head, 20);
print(head);
printf("Linked list after inserting the node:5 at the end \n");
insertAtEnd(&head, 5);
print(head);
printf("Linked list after inserting the node:30 at the end \n");
insertAtEnd(&head, 30);
print(head);
printf("Linked list after inserting the node:15 at position 2 \n");
insertAtPosition(&head, 15, 2);
print(head);
printf("Linked list after deleting the first node: \n");
deleteFromFirst(&head);
print(head);
printf("Linked list after deleting the last node: \n");
deleteFromEnd(&head);
print(head);
printf("Linked list after deleting the node at position 1: \n");
deleteAtPosition(&head, 1);
print(head);
return 0;
}
```

---

## Experiment 7: Implement Doubly Linked List

```c
// C Program to Implement Doubly Linked List 
#include <stdio.h> 
#include <stdlib.h> 
// defining a node 
typedef struct Node { 
int data; 
struct Node* next; 
struct Node* prev; 
} Node; 
// Function to create a new node with given value as data 
Node* createNode(int data) 
{ 
Node* newNode = (Node*)malloc(sizeof(Node)); 
newNode->data = data; 
newNode->next = NULL; 
newNode->prev = NULL; 
return newNode; 
} 
// Function to insert a node at the beginning 
void insertAtBeginning(Node** head, int data) 
{// creating new node 
Node* newNode = createNode(data); 
// check if DLL is empty 
if (*head == NULL) { 
*head = newNode; 
return; 
} 
newNode->next = *head; 
(*head)->prev = newNode; 
*head = newNode; 
} 
// Function to insert a node at the end 
void insertAtEnd(Node** head, int data) 
{ 
// creating new node 
Node* newNode = createNode(data); 
// check if DLL is empty 
if (*head == NULL) { 
*head = newNode; 
return; 
} 
Node* temp = *head;while (temp->next != NULL) { 
temp = temp->next; 
} 
temp->next = newNode; 
newNode->prev = temp; 
} 
// Function to insert a node at a specified position 
void insertAtPosition(Node** head, int data, int position) 
{ 
if (position < 1) { 
printf("Position should be >= 1.\n"); 
return; 
} 
// if we are inserting at head 
if (position == 1) { 
insertAtBeginning(head, data); 
return; 
} 
Node* newNode = createNode(data); 
Node* temp = *head; 
for (int i = 1; temp != NULL && i < position - 1; i++) { 
temp = temp->next; 
}if (temp == NULL) { 
printf( 
"Position greater than the number of nodes.\n"); 
return; 
} 
newNode->next = temp->next; 
newNode->prev = temp; 
if (temp->next != NULL) { 
temp->next->prev = newNode; 
} 
temp->next = newNode; 
} 
// Function to delete a node from the beginning 
void deleteAtBeginning(Node** head) 
{ 
// checking if the DLL is empty 
if (*head == NULL) { 
printf("The list is already empty.\n"); 
return; 
} 
Node* temp = *head; 
*head = (*head)->next;if (*head != NULL) { 
(*head)->prev = NULL; 
} 
free(temp); 
} 
// Function to delete a node from the end 
void deleteAtEnd(Node** head) 
{ 
// checking if DLL is empty 
if (*head == NULL) { 
printf("The list is already empty.\n"); 
return; 
} 
Node* temp = *head; 
if (temp->next == NULL) { 
*head = NULL; 
free(temp); 
return; 
} 
while (temp->next != NULL) { 
temp = temp->next; 
} 
temp->prev->next = NULL;free(temp); 
} 
// Function to delete a node from a specified position 
void deleteAtPosition(Node** head, int position) 
{ 
if (*head == NULL) { 
printf("The list is already empty.\n"); 
return; 
} 
Node* temp = *head; 
if (position == 1) { 
deleteAtBeginning(head); 
return; 
} 
for (int i = 1; temp != NULL && i < position; i++) { 
temp = temp->next; 
} 
if (temp == NULL) { 
printf("Position is greater than the number of " 
"nodes.\n"); 
return; 
}if (temp->next != NULL) { 
temp->next->prev = temp->prev; 
} 
if (temp->prev != NULL) { 
temp->prev->next = temp->next; 
} 
free(temp); 
} 
// Function to print the list in forward direction 
void printListForward(Node* head) 
{ 
Node* temp = head; 
printf("Forward List: "); 
while (temp != NULL) { 
printf("%d ", temp->data); 
temp = temp->next; 
} 
printf("\n"); 
} 
// Function to print the list in reverse direction 
void printListReverse(Node* head) 
{ 
Node* temp = head;if (temp == NULL) { 
printf("The list is empty.\n"); 
return; 
} 
// Move to the end of the list 
while (temp->next != NULL) { 
temp = temp->next; 
} 
// Traverse backwards 
printf("Reverse List: "); 
while (temp != NULL) { 
printf("%d ", temp->data); 
temp = temp->prev; 
} 
printf("\n"); 
} 
int main() 
{ 
Node* head = NULL; 
// Demonstrating various operations 
insertAtEnd(&head, 10); 
insertAtEnd(&head, 20);insertAtBeginning(&head, 5); 
insertAtPosition(&head, 15, 2); // List: 5 15 10 20 
printf("After Insertions:\n"); 
printListForward(head); 
printListReverse(head); 
deleteAtBeginning(&head); // List: 15 10 20 
deleteAtEnd(&head); // List: 15 10 
deleteAtPosition(&head, 2); // List: 15 
printf("After Deletions:\n"); 
printListForward(head); 
return 0; 
}
```

---

## Experiment 8: Implement a program on Insertion sorting technique

```c
#include<stdio.h> 
// main function definition 
int main() 
{ 
int a[10], n, i, j, k, temp; 
printf("Enter size of array or list: \n"); 
scanf("%d",&n); 
printf("Enter values in the array: \n"); 
for(i=0;i<n;i++) 
{scanf("%d",&a[i]); 
} 
printf("Array elements before sorting: \n"); 
for(i=0; i<n; i++) 
{ 
printf("%d\t", a[i]); 
} 
//insertion sort 
//n = number of elements in array. 
//temp = temporary variable which we want to insert into already sorted array 
// k= total number of passes. 
//j = control variable used for internal comparison 
for(k=0; k<n; k++) 
{ 
temp = a[k]; 
j=k-1; 
while((a[j]>temp)&&(j>=0)) 
{ 
a[j+1]=a[j]; 
j--; 
} 
a[j+1]=temp; 
} 
printf("\nArray elements After insertion sort:\n"); 
for(i=0;i<n;i++) 
{ 
printf("%d\t", a[i]);} 
return 0; 
}
```

---

## Experiment 9: Implement a program on Selection sorting technique

```c
#include <stdio.h> 
int main() { 
int arr[50], n, i, j, min, temp; 
printf("Enter number of elements: "); 
scanf("%d", &n); 
printf("Enter elements:\n"); 
for(i = 0; i < n; i++) { 
scanf("%d", &arr[i]); 
} 
// Selection Sort 
for(i = 0; i < n - 1; i++) { 
min = i;for(j = i + 1; j < n; j++) { 
if(arr[j] < arr[min]) { 
min = j; 
} 
} 
// Swap the found minimum element with the first element 
temp = arr[i]; 
arr[i] = arr[min]; 
arr[min] = temp; 
} 
printf("Sorted array:\n"); 
for(i = 0; i < n; i++) { 
printf("%d ", arr[i]); 
} 
return 0; 
}
```

---

## Experiment 10: Implementation of Binary Search Tree and its traversal methods

```c
#include <stdio.h> 
#include <stdlib.h> 
// Structure of a tree node 
struct Node 
{int data; 
struct Node* left; 
struct Node* right; 
}; 
// Function to create a new node 
struct Node* createNode(int value) 
{ 
struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); 
newNode->data = value; 
newNode->left = NULL; 
newNode->right = NULL; 
return newNode; 
} 
// Preorder Traversal (Root -> Left -> Right) 
void preorder(struct Node* root) 
{ 
if(root == NULL) 
return; 
printf("%d ", root->data); 
preorder(root->left); 
preorder(root->right); 
} 
// Inorder Traversal (Left -> Root -> Right) 
void inorder(struct Node* root) 
{if(root == NULL) 
return; 
inorder(root->left); 
printf("%d ", root->data); 
inorder(root->right); 
} 
// Postorder Traversal (Left -> Right -> Root) 
void postorder(struct Node* root) 
{ 
if(root == NULL) 
return; 
postorder(root->left); 
postorder(root->right); 
printf("%d ", root->data); 
} 
// Main function 
int main() 
{ 
struct Node* root = createNode(1); 
root->left = createNode(2); 
root->right = createNode(3); 
root->left->left = createNode(4); 
root->left->right = createNode(5); 
printf("Preorder Traversal: ");preorder(root); 
printf("\nInorder Traversal: "); 
inorder(root); 
printf("\nPostorder Traversal: "); 
postorder(root); 
return 0; 
}
```

---

## Experiment 11: Implementation of DFS and BFS

```c
#include <stdio.h> 
#define MAX 10 
int adj[MAX][MAX], visited[MAX]; 
int queue[MAX], front = -1, rear = -1; 
int n; 
// Queue operations for BFS 
void enqueue(int v) 
{ 
if(rear == MAX-1) 
return; 
if(front == -1) 
front = 0; 
queue[++rear] = v; 
} 
int dequeue() 
{ 
if(front == -1) 
return -1; 
int item = queue[front]; 
if(front == rear) 
front = rear = -1; 
else 
front++; 
return item; 
}// BFS Traversal 
void bfs(int start) 
{ 
int i, v; 
for(i = 0; i < n; i++) 
visited[i] = 0; 
enqueue(start); 
visited[start] = 1; 
printf("BFS Traversal: "); 
while(front != -1) 
{ 
v = dequeue(); 
printf("%d ", v); 
for(i = 0; i < n; i++) 
{ 
if(adj[v][i] == 1 && visited[i] == 0) 
{ 
enqueue(i); 
visited[i] = 1; 
} 
} 
} 
}// DFS Traversal 
void dfs(int v) 
{ 
int i; 
visited[v] = 1; 
printf("%d ", v); 
for(i = 0; i < n; i++) 
{ 
if(adj[v][i] == 1 && visited[i] == 0) 
dfs(i); 
} 
} 
int main() 
{ 
int i, j, start; 
printf("Enter number of vertices: "); 
scanf("%d", &n); 
printf("Enter adjacency matrix:\n"); 
for(i = 0; i < n; i++) 
{ 
for(j = 0; j < n; j++) 
{scanf("%d", &adj[i][j]); 
} 
} 
printf("Enter starting vertex: "); 
scanf("%d", &start); 
bfs(start); 
for(i = 0; i < n; i++) 
visited[i] = 0; 
printf("\nDFS Traversal: "); 
dfs(start); 
return 0; 
}
```

---

## Experiment 12: Implement a program on Binary searching

```c
#include <stdio.h> 
int binarySearch(int arr[], int n, int key) { 
int low = 0, high = n - 1, mid; 
while (low <= high) { 
mid = (low + high) / 2; 
if (arr[mid] == key) 
return mid; 
else if (key < arr[mid]) 
high = mid - 1;else 
low = mid + 1; 
} 
return -1; 
} 
int main() { 
int arr[100], n, key, i, result; 
printf("Enter number of elements: "); 
scanf("%d", &n); 
printf("Enter sorted elements:\n"); 
for (i = 0; i < n; i++) { 
scanf("%d", &arr[i]); 
} 
printf("Enter element to search: "); 
scanf("%d", &key); 
result = binarySearch(arr, n, key); 
if (result != -1) 
printf("Element found at position %d\n", result + 1); 
else 
printf("Element not found\n"); 
return 0; 
}
```

---
