<h1 align="center">Data Structures: Stacks + Queues</h1>

### Section overview
* **[Stacks](#stacks)**
* **[Queues](#queues)**
* **[Stack Implementation (Linked Lists)](#stack-linked-lists)**
* **[Stack Implementation (Array)](#stack-array)**
* **[Queue Implementation](#queue-implementation)**
* **[Stacks + Queues Review](#stacks-queues)**




### Stacks 

A stack is a linear data structure that follows the LIFO (Last In First Out) principle. 

This means that the most recent item added to the stack is the first item to be removed. 

Stacks are often used to implement undo/redo functionality, expression evaluation, and function call tracking.

LIFO - Last in, First Out

![Stacks](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/17.png)

### Queues

Queue is a linear data structure in which elements are added to one end (the back) and removed from the other end (the front). 

This makes queues a type of FIFO (First In, First Out) data structure, meaning that the first element added to the queue is the first element removed.

FIFO - First In, First Out

![Queues](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/18.png)

#
**[Back to The TOP](#section-overview)**

### <a name="stack-linked-lists">Stack Implementation (Linked Lists)</a>

**JavaScript Class**:
```
class Node {
    constructor(value) {
      this.value = value;
      this.next = null;
    }
  }
  
  class Stack {
    constructor() {
      this.top = null;
      this.bottom = null;
      this.length = 0;
    }
    peek() {
      return this.top;
    }
    push(value) {
      const newNode = new Node(value);
      if (this.length === 0) {
        this.top = newNode;
        this.bottom = newNode;
      } else {
        const holdingPointer = this.top;
        this.top = newNode;
        this.top.next = holdingPointer;
      }
      this.length++;
      return this;
    }
    pop() {
      if (!this.top) {
        return null;
      }
      if (this.top === this.bottom) {
        this.bottom = null;
      }
      // const holdingPointer = this.top;
      this.top = this.top.next;
      this.length--;
      return this;
    }
    //isEmpty
  }
  
  const myStack = new Stack();
  console.log(myStack.push("google"));
  console.log(myStack.push("google2"));
  console.log(myStack.peek());
  console.log(myStack.pop());
  console.log(myStack.pop());
  //Discord
  //ZTM
  //google
```
[Core Link](https://github.com/aneagoie/ztm-master-the-coding-interview-ds-algo/blob/main/04_stacks/stackImplementation.js)
#
**[Back to The TOP](#section-overview)**

### <a name="stack-array">Stack Implementation (Array)</a>

**JavaScript Class**:

```
class Stack {
    constructor(){
      this.array = [];
    }
    peek() {
      return this.array[this.array.length-1];
    }
    push(value){
      this.array.push(value);
      return this;
    }
    pop(){
      this.array.pop();
      return this;
    }
  }
  
  const myStack = new Stack();
  myStack.peek();
  myStack.push('google');
  myStack.push('ztm');
  myStack.push('discord');
  myStack.peek();
  myStack.pop();
  myStack.pop();
  myStack.pop();

  //Discord
  //ZTM
  //google
```
[Core Link](https://github.com/aneagoie/ztm-master-the-coding-interview-ds-algo/blob/main/04_stacks/stackArrayImplementation.js)
#
**[Back to The TOP](#section-overview)**

### Queue Implementation

**JavaScript Class**:

```
class Node {
    constructor(value) {
      this.value = value;
      this.next = null;
    }
  }
  
  class Queue {
    constructor() {
      this.first = null;
      this.last = null;
      this.length = 0;
    }
    peek() {
      return this.first;
    }
    enqueue(value) {
      const newNode = new Node(value);
      if (this.length === 0) {
        this.first = newNode;
        this.last = newNode;
      } else {
        this.last.next = newNode;
        this.last = newNode;
      }
      this.length++;
      return this;
    }
    dequeue() {
      if (!this.first) {
        return null;
      }
      if (this.first === this.last) {
        this.last = null;
      }
      this.first = this.first.next;
      this.length--;
      return this;
    }
    //isEmpty;
  }
  
  const myQueue = new Queue();
  myQueue.enqueue("Joy");
  myQueue.enqueue("Matt");
  myQueue.enqueue("Pavel");
  myQueue.enqueue("Samir");
  myQueue.dequeue();
  myQueue.peek();
  console.log(myQueue);
  //Joy
  //Matt
  //Pavel
  //Samir
```
#
**[Back to The TOP](#section-overview)**

### <a name="stacks-queues">Stacks + Queues Review</a>

![Stacks + Queues Review](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/19.JPG)

**[Back to The TOP](#section-overview)**


How Does Javascript Work?

JavaScript is a single threaded language that can be non blocking.

What is a program?
    - allocate memory
    - parse and execute 

What is a Memory Heap?

What is Memory Leak?

What is Call Stack? FILO - First in Last Out
en
What is a Synchronous programming? -  line one gets executed, then line two gets executed, and then

Create Stack Overflow:

And recursion means a function that calls itself.

function foo(){
    foo()
}

Javascript is a single threaded language that can be non-blocking?

Well, asynchronous to the rescue.


What is JavaScript Run-Time Environment

