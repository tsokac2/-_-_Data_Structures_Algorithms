<h1 align="center">Data Structures: Introduction</h1>

### Section overview
* **[What Is A Data Structure?](#data-structure)**
* **[How Computers Store Data](#how-computers-store-data)**
* **[Operations On Data Structures](#operations-on-data-structures)**

### <a name="data-structure">What Is A Data Structure?</a>
A data structure is a collection of values. The values can have relationships among them, and they can have functions apply to them.

Arrays and objects in JavaScript are each a form of a data structure that allows us to store information.

It refers to the logical or mathematical representation of data, as well as the implementation in a computer program. 

Data structures are essential for efficient program design, as they allow programmers to store, retrieve, and manipulate data in a way that is both fast and easy to understand.

**[Back to The TOP](#section-overview)**
#

### How Computers Store Data

**CPU - Central Processing Unit**
- It is the brains of a computer, responsible for carrying out all the instructions that make your computer work. 
- The **CPU** is made up of several different components, including the control unit, the arithmetic logic unit (ALU), and the registers.

**RAM - Random access memory**

- Primary storage is the memory that is directly accessible by the computer's central processing unit (CPU). 
- It is typically volatile, meaning that it loses its contents when the computer is powered off. 


A data structure is an arrangement of data.
You can define the way you interact with this data and how it is arranged in RAM.

**[Back to The TOP](#section-overview)**
#

### Data Structures In Different Languages

#### Arrays
An array is a collection of elements, each identified by an index or a key.
```
// Declaration of an array
let myArray = [1, 2, 3, 4, 5];

// Accessing elements
console.log(myArray[2]);  // Output: 3

// Modifying an element
myArray[1] = 10;
```
#### Stacks
A stack is a Last In, First Out (LIFO) data structure where elements are added and removed from the same end.
```
// Using an array as a stack
let myStack = [3, 4, 5];

// Pushing an element onto the stack
myStack.push(6);

// Popping the last element
let poppedElement = myStack.pop();
```

#### Queues
A queue is a First In, First Out (FIFO) data structure where elements are added at the rear and removed from the front.
```
// Using an array as a queue
let myQueue = [1, 2, 3];

// Enqueue an element
myQueue.push(4);

// Dequeue the front element
let dequeuedElement = myQueue.shift();
```
#### Linked Lists
A linked list is a collection of nodes where each node points to the next node in the sequence.
#### Trees
A tree is a hierarchical data structure with a root element and subtrees of child elements.

#### Tries
A trie is a tree-like data structure used for storing an associative array where keys are sequences.

#### Graphs
A graph is a collection of nodes (vertices) and edges connecting these nodes.

#### Hash Tables
A hash table is a data structure that implements an associative array abstract data type.
```
// Using an object as a hash table
let myHashTable = {};
myHashTable["key1"] = "value1";
```
![Data Structures Language Support](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/03.JPG)

**[Back to The TOP](#section-overview)**
#

### Operations On Data Structures
![Operations On Data Structures](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/04.JPG)

#### Arrays:
- **Access**: Retrieve the value at a specific index.
- **Insertion**: Add a new element at a given position or at the end.
- **Deletion**: Remove an element from a specific position or based on its value.
- **Search**: Find the index or presence of a specific element.

#### Linked Lists:
- **Insertion**: Add a new node at the beginning, end, or a specific position.
- **Deletion**: Remove a node from the beginning, end, or a specific position.
- **Traversal**: Visit each node in sequence.
- **Search**: Find a node with a specific value.

#### Stacks:

- **Push**: Add an element to the top of the stack.
- **Pop**: Remove the element from the top of the stack.
- **Peek**: View the element at the top without removing it.
- **isEmpty**: Check if the stack is empty.

#### Queues:
- **Enqueue**: Add an element to the rear/end of the queue.
- **Dequeue**: Remove the element from the front.
- **Front/Rear**: Get the element at the front or rear without removing it.
- **isEmpty**: Check if the queue is empty.

#### Trees:

- **Insertion**: Add a new node.
- **Deletion**: Remove a node.
- **Traversal**: Visit nodes in a specific order (in-order, pre-order, post-order).
- **Search**: Find a node with a specific value.

#### Graphs:

- **Add Vertex/Edge**: Include a new node or connection between nodes.
- **Remove Vertex/Edge**: Delete a node or connection.
- **Traversal**: Visit nodes based on certain algorithms (DFS, BFS).
- **Search**: Find a node or path between nodes.

**[Back to The TOP](#section-overview)**
#