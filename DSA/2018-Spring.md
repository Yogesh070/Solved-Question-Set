# 2018-Spring

## 1. a) Define abstract data types? Justify the statement "Data structure is the backbone of software Programming".

Ans: Abstract Data type (ADT) is a type (or class) for objects whose behaviour is defined by a set of value and a set of operations.
The definition of ADT only mentions what operations are to be performed but not how these operations will be implemented. It does not specify how data will be organized in memory and what algorithms will be used for implementing the operations. It is called “abstract” because it gives an implementation-independent view. The process of providing only the essentials and hiding the details is known as abstraction.

Data structures are the way we are able to store and retrieve data.At the backbone of every program or piece of software are two entities: data and algorithms. Algorithms transform data into something a program can effectively use. Therefore, it is important to understand how to structure data so algorithms can maintain, utilize, and iterate through data quickly.
With a slight thinking , we can guess that the way we organize information can have a lot of impact on the performance. Take for example, a library. Suppose, you want to have a book on Set Theory from a public library, to do that you have to first go to the maths section, then to set theory section. If these books are not organized in this manner and just distributed randomly then it will be really a cumbersome process to find a book on set theory.
This is the way a librarian organizes his books(data) into a particular form (data structure) to efficiently perform a task(find a book on set theory).In this manner we computer scientist process and look for the best way we can organize the data we have, so it can be better processed based on input provided.
Use of Data structure in software programming helps in:

- Efficient Memory use and hence the software is optimized.
-Data structures can be reused, i.e. once we have implemented a particular data structure, we can use it at any other place. Implementation of data structures can be compiled into libraries which can be used by different clients.
- Data structure serves as the basis of abstract data in software programming.

## 1. b) Write the advantages of Postfix expression over the Infix expression. Convert the given expression into Postfix expression showing the content of stack at each step.(A+B*C/D)+E*F-(G*H+I-J).

Ans:
Infix Notation
We write expression in infix notation, e.g. a - b + c, where operators are used in-between operands. It is easy for us humans to read, write, and speak in infix notation but the same does not go well with computing devices. An algorithm to process infix notation could be difficult and costly in terms of time and space consumption.

Postfix Notation
This notation style is known as Reversed Polish Notation. In this notation style, the operator is postfixed to the operands i.e., the operator is written after the operands. For example, ab+. This is equivalent to its infix notation a + b.

 The advantages of Postfix expression over the Infix expression are as follow:

- Any formula can be expressed without parenthesis.
It is very convenient for evaluating formulas on computer with stacks.
- Postfix expression doesn't has the operator precedence.
- Postfix is slightly easier to evaluate.
- It reflects the order in which operations are performed.
-You need to worry about the left and right associativity.

## 2. a) Differentiate between recursion adn iteration. Write a recursive mechanism (algorithm)for solving tower of hanoi problem

Ans:
| Basis for comparision | Recursion | Iteration
| ----------------------|-----------|----------
Basic | The statement in a body of function calls the function itself. | Allows the set of instructions to be repeatedly executed.
Format | In recursive function, only termination condition (base case) is specified. | Iteration includes initialization, condition, execution of statement within loop and update (increments and decrements) the control variable.
Termination	| A conditional statement is included in the body of the function to force the function to return without recursion call being executed. | The iteration statement is repeatedly executed until a certain condition is reached.
Condition | If the function does not converge to some condition called (base case), it leads to infinite recursion. | If the control condition in the iteration statement never become false, it leads to infinite iteration.
Infinite Repetition| Infinite recursion can crash the system. | Infinite loop uses CPU cycles repeatedly.
Stack | The stack is used to store the set of new local variables and parameters each time the function is called. | Does not uses stack.
Speed |  Slow in execution. |  Fast in execution.
Size of Code | Recursion reduces the size of the code. | Iteration makes the code longer.
Applied | Recursion is always applied to functions. | Iteration is applied to iteration statements or "loops". |

```javascript
// C++ recursive function to solve tower of hanoi puzzle 
#include <bits/stdc++.h> 
using namespace std; 

void towerOfHanoi(int n, char from_rod,char to_rod, char aux_rod)
{
	if (n == 1)
	{ 
	cout << "Move disk 1 from rod " << from_rod <<" to rod " << to_rod<<endl; 
	return;
	} 
	towerOfHanoi(n - 1, from_rod, aux_rod, to_rod);
	cout << "Move disk " << n << " from rod " << from_rod <<" to rod " << to_rod << endl; 
	towerOfHanoi(n - 1, aux_rod, to_rod, from_rod);
} 

// Driver code
int main()
{
	int n = 4; // Number of disks
	towerOfHanoi(n, 'A', 'C', 'B'); // A, B and C are names of rods 
	return 0;
}
```

## 2. b) Explain the advantages of doubly linked list implementation. Write algorithm for insertion and deletion in stack as linked list.

Ans: Doubly linked list is a collection of nodes linked together in a sequential way. Each node of the list contains two parts (as in singly linked list) data part and the reference or address part. Advantages of doubly linked list implementation are as follows:

1) A DLL can be traversed in both forward and backward direction.
2) The delete operation in DLL is more efficient if pointer to the node to be deleted is given.
3) We can quickly insert a new node before a given node.
In singly linked list, to delete a node, pointer to the previous node is needed. To get this previous node, sometimes the list is traversed. In DLL, we can get the previous node using previous pointer.

////2nd part not added//

## 3. a) Explain with example the different cases of balancing AVL tree after inserting a node that violates the property.

Ans: In AVL tree, after performing every operation like insertion and deletion we need to check the balance factor of every node in the tree. If every node satisfies the balance factor condition then we conclude the operation otherwise we must make it balanced. We use rotation operations to make the tree balanced whenever the tree is becoming imbalanced due to any operation.There are four rotations and they are classified into two types:

- Single Left Rotation (LL Rotation)
In LL Rotation every node moves one position to left from the current position.Example:3is right child of 2, 2 is right child of 1. 2 becomes the new root, 1 takes ownership of any 2's left child, and 3 takes ownership of any 2's right child.

![Left Rotation](https://qph.fs.quoracdn.net/main-qimg-4909912ad7731393577f2482594a0753.webp)

- Single Right Rotation (RR Rotation)
In RR Rotation every node moves one position to right from the current position.Example:3 is left child of 4, 4 is left child of 5. 4 becomes the new root, 3 takes ownership of any 4's left child, and 5 takes ownership of any 5's right child.

![Right Rotation](https://qph.fs.quoracdn.net/main-qimg-96adcd2021787abfc018e0335ba877ea.webp)

- Left Right Rotation (LR Rotation)
The LR Rotation is combination of single left rotation followed by single right rotation. In LR Rotation, first every node moves one position to left then one position to right from the current position. Performing a Right-rotation on the right Subtree, prepares for the definitive Left-rotation. 6 becomes the root of the Subtree having 8 as right child; finally, 6 becomes the root of the Tree, having 5 as left child and 8 as right child.

![Left Right Rotation](https://qph.fs.quoracdn.net/main-qimg-99e0cda76398e114ac33346ea431a376.webp)

- Right Left Rotation (RL Rotation)
The RL Rotation is combination of single right rotation followed by single left rotation. In RL Rotation, first every node moves one position to right then one position to left from the current position.Example: 7becomes the root of the Subtree having 6 as left child; finally 7 becomes the root of the Tree, having 6 as left child and 8 as right child.

![Right Left Rotation](https://qph.fs.quoracdn.net/main-qimg-c036fbcb64ccd101f42f2abee488ad9d.webp)

## 3. b) Construct a BST from the following data and show VLR, LRV,LVR and RVL traversals 14,10,17,12,11,20,18,25,20,8,23,23

Ans: //// not added//

## 4. a) Define queue. Mention the primitive operation of queue and write the module for enqueuer and dequeuer in Circular queue.

Ans: A Queue is a linear structure which follows a particular order in which the operations are performed. The order is First In First Out (FIFO).

The primitive operation of queue are as follows:

- enqueue() − add (store) an item to the queue.
- dequeue() − remove (access) an item from the queue.
- peek() − Gets the element at the front of the queue without removing it.
- isfull() − Checks if the queue is full.
- isempty() − Checks if the queue is empty.

 The module for enqueuer and dequeuer in Circular queue are:

* enQueue(value) This function is used to insert an element into the circular queue. In a circular queue, the new element is always inserted at Rear position.
Steps:

- Check whether queue is Full – Check ((rear == SIZE-1 && front == 0) || (rear == front-1)).
- If it is full then display Queue is full. If queue is not full then, check if (rear == SIZE – 1 && front != 0) if it is true then set rear=0 and insert element.

* deQueue() This function is used to delete an element from the circular queue. In a circular queue, the element is always deleted from front position.
Steps:

- Check whether queue is Empty means check (front==-1).
- If it is empty then display Queue is empty. If queue is not empty then step 3
Check if (front==rear) if it is true then set front=rear= -1 else check if (front==size-1), if it is true then set front=0 and return the element.

## 4. b) Generate the Huffman code and also draw the huffman tree for the following unique character "POKHARAUNIVERSITY".

Ans:
Character | Frequency
----------|----------
P | 1
O | 1
K | 1
H | 1
A | 2
R | 2
U | 1
N | 1
I | 2
V | 1
E | 1
S | 1
T | 1
Y | 1

Sort the data values in ascending order with its frequency:
Character | Frequency
----------|----------
P | 1
O | 1
K | 1
H | 1
V | 1
E | 1
S | 1
T | 1
Y | 1
U | 1
N | 1
A | 2
R | 2
I | 2

## 5. a) What is sorting. Write an algorithm for quick sort.

Ans: Sorting is any process of arranging items systematically. Sorting algorithm specifies the way to arrange data in a particular order.

Recursive algorithm for quicksort as follows −

- Step 1 − Make the right-most index value pivot
- Step 2 − partition the array using pivot value
- Step 3 − quicksort left partition recursively
- Step 4 − quicksort right partition recursively

## 5. b) What is collision in hashing? What are the collision resolving techniques in hashing? Explain seperate chaining.

Ans: Since a hash function gets us a small number for a key which is a big integer or string, there is a possibility that two keys result in the same value. The situation where a newly inserted key maps to an already occupied slot in the hash table is called collision and must be handled using some collision handling technique.

There are mainly two methods to resolving collision:

1. Separate Chaining
2. Open Addressing

#### Separate Chaining

Separate chaining is defined as a method by which linked lists of values are built in association with each location within the hash table when a collision occurs.
The concept of separate chaining involves a technique in which each index key is built with a linked list. This means that the table's cells have linked lists governed by the same hash function.
Example:

![Seperate Chaining Collision](https://study.com/cimages/multimages/16/sep_chain_1.png)

The figure shows incidences of collisions in different table locations. We'll assign strings as our input data: [John, Janet, Mary, Martha, Claire, Jacob, and Philip]. Our hash table size is 6. As the strings are evaluated at input through the hash functions, they are assigned index keys (0, 1, 2, 3, 4, or 5). We store the first string John, then Janet and Mary. All is fine, but when we try to store Martha, the hash function assigns Martha the same index key as Janet. Now, because a second value is attempting to map to an already occupied index key, a collision occurs as seen in figure we've been using. Three out of the six locations are occupied, and the probability that the remaining strings yet to be loaded will cause other collisions is very high.

So, in place of the collision error which occurred in the figure we used in the last section, the cell now contains a linked list containing the string 'Janet' and 'Martha' as seen in this new figure. We can see in this figure how the subsequent strings are loaded using the separate chaining technique.

![Seperate Chaining](https://study.com/cimages/multimages/16/sep_chain2.png)

## 6. a) Define Graph and digraphs. Explain Adjacency matrix representation of graph with examples in unidirected and directed graph.

Ans: A graph is a pictorial representation of a set of objects where some pairs of objects are connected by links.

A directed graph (or digraph) is a set of vertices and a collection of directed edges that each connects an ordered pair of vertices.

An adjacency matrix is a way of representing a graph G = {V, E} as a matrix of booleans.

//second part not added//

## 6. b) Define minimal spanning tree. Explain Kruskal's Algorithm for finding the minimum spanning tree.

Ans: The cost of the spanning tree is the sum of the weights of all the edges in the tree. There can be many spanning trees. Minimum spanning tree is the spanning tree where the cost is minimum among all the spanning trees.

Kruskal’s Algorithm builds the spanning tree by adding edges one by one into a growing spanning tree. Kruskal's algorithm follows greedy approach as in each iteration it finds an edge which has least weight and add it to the growing spanning tree.

Algorithm Steps:

- Sort the graph edges with respect to their weights.
- Start adding edges to the MST from the edge with the smallest weight until the edge of the largest weight.
- Only add edges which doesn't form a cycle , edges which connect only disconnected components.

Consider following example:

![Kruskals algorithm](https://he-s3.s3.amazonaws.com/media/uploads/6322896.jpg)

## 7. Short notes on:

### 1. TOH problem

Tower of Hanoi is a mathematical puzzle where we have three rods and n disks. The objective of the puzzle is to move the entire stack to another rod, obeying the following simple rules:

- Only one disk can be moved at a time.
- Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack i.e. a disk can only be moved if it is the uppermost disk on a stack.
- No disk may be placed on top of a smaller disk.
  
For n disks, total 2^n – 1 moves are required.

### 2. Deterministic and non-deterministic algorithm

In deterministic algorithm, for a given particular input, the computer will always produce the same output going through the same states but in case of non-deterministic algorithm, for the same input, the compiler may produce different output in different runs. In fact non-deterministic algorithms can’t solve the problem in polynomial time and can’t determine what is the next step. The non-deterministic algorithms can show different behaviors for the same input on different execution and there is a degree of randomness to it.

DETERMINISTIC ALGORITHM | NON-DETERMINISTIC ALGORITHM
------------------------|----------------------------
For a particular input the computer will give always same output. | For a particular input the computer will give different output on different execution.
Can solve the problem in polynomial time. | Can’t solve the problem in polynomial time.
Can determine the next step of execution. | Cannot determine the next step of execution due to more than one path the algorithm can take.

### 3.Static vs dynamic list

Static Data structure has fixed memory size whereas in Dynamic Data Structure, the size can be randomly updated during run time which may be considered efficient with respect to memory complexity of the code. Static Data Structure provides more easier access to elements with respect to dynamic data structure. Unlike static data structures, dynamic data structures are flexible.