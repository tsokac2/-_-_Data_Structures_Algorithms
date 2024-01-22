<h1 align="center">Data Structures: Linked Lists</h1>

### Section overview
* **[What Is A Linked List?](#linked-lists)**
* **[Why Linked Lists?](#why-linked-lists)**
* **[What Is A Pointer?](#pointer)**
* **[Linked List in JavaScript](#linked-list-in-javaScript)**
* **[Doubly Linked Lists](#doubly-Linked-lists)**
* **[Doubly Linked Lists in JavaScript](#doubly-linked-lists-in-javaScript)**
* **[Singly VS Doubly Linked Lists](#singly-vs-doubly-linked-lists)**
* **[Exercise: reverse()](#e-reverse)**
* **[Linked Lists Review](#linked-lists-review)**

### <a name="linked-lists">What Is A Linked List?</a>

A linked list is a data structure used in computer science to organize and store data. 

It consists of a sequence of elements, each of which contains a reference (or link) to the next element in the sequence. 

Unlike arrays, linked lists do not require contiguous memory locations, allowing for dynamic memory allocation and efficient insertion or removal of elements at any position within the list.

### <a name="why-linked-lists">Why Linked Lists?</a>

- **Dynamic Size:** Unlike arrays, linked lists can dynamically adjust their size during runtime.

- **Efficient Insertions and Deletions**: Inserting or deleting elements in a linked list is more efficient than in an array, especially when dealing with large datasets.

- **No Contiguous Memory Requirement**: Linked lists do not require contiguous memory locations, allowing for more efficient memory utilization.

- **Easy to Implement Certain Algorithms**: Some algorithms, like certain graph algorithms, are more naturally implemented with linked lists.

- **Simplifying Memory Management**: Memory can be allocated and deallocated more dynamically in linked lists compared to arrays.

![Why Linked Lists](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/14.JPG)

#
**[Back to The TOP](#section-overview)**

### <a name="pointer">What Is A Pointer?</a>

It's a reference to another place in memory or another object or another node.

```
const obj1 = { a: true}
const obj2 = obj1; // this is a pointer or a refrence to obj1
```

```
Node 1: [Data: A] -> [Next: Address of Node 2]
Node 2: [Data: B] -> [Next: Address of Node 3]
Node 3: [Data: C] -> [Next: NULL]
```

In this example, each node contains a data field (A, B, C) and a next pointer, forming a singly linked list. 

The next pointer of Node 1 holds the address of Node 2, and the next pointer of Node 2 holds the address of Node 3. 

The last node's next pointer is typically set to NULL to indicate the end of the list.

#
**[Back to The TOP](#section-overview)**

### Linked List in JavaScript

JavaScript ``class`` for creating Linked List
```
class LinkedList {
    constructor(value) {
        this.head = {
            value: value ,
            next: null
        }
        this.tail = this.head;
        this.length = 1;
    }

// append - add to the end of the Linked List
   append(value) {
    const newNode = {
      value: value,
      next: null
    }
    console.log(newNode)
    this.tail.next = newNode;
    this.tail = newNode;
    this.length++;
    return this;
  }

// prepend - add to the begining of the Linked List
    prepend(value) {
    const newNode = {
      value: value,
      next: null
    }
    newNode.next = this.head;
    this.head = newNode;
    this.length++;
    return this;
  }

// print list in array format in the console

    printList() {
      const array = [];
      let currentNode = this.head;
      while(currentNode !== null){
          array.push(currentNode.value)
          currentNode = currentNode.next
      }
      return array;
    }

// insert elements between another elements in linked list 
   insert(index, value){
    //Check for proper parameters;
      if(index === 0) {
        this.prepend(value);
        return this.printList();
      }
      
      const newNode = {
        value: value,
        next: null
      }

      const leader = this.traverseToIndex(index-1);
      const holdingPointer = leader.next;
      leader.next = newNode;
      newNode.next = holdingPointer;
      this.length++;
      return this.printList();
    }

    traverseToIndex(index) {
      //Check parameters
      let counter = 0;
      let currentNode = this.head;
      while(counter !== index){
        currentNode = currentNode.next;
        counter++;
      }
      return currentNode;
    }

// remove elements from the linked list
   remove(index) {
      // Check Parameters      
      const leader = this.traverseToIndex(index-1);
      const unwantedNode = leader.next;
      leader.next = unwantedNode.next;
      this.length--;
      return this.printList();
    }

}

let myLinkedList = new LinkedList(10);
myLinkedList.append(5);
myLinkedList.append(16);
```
[Core Link](https://github.com/aneagoie/ztm-master-the-coding-interview-ds-algo/blob/main/03_linkedLists/linkedListImplementation.js)

#
**[Back to The TOP](#section-overview)**

### Doubly Linked Lists

A Doubly Linked List is a type of linked list where each element, in addition to holding data, has two pointers. 

These pointers are references to both the next and the previous elements in the sequence. 

Unlike a singly linked list, where each element points only to the next one, a doubly linked list allows for bidirectional traversal.

![Doubly Linked Lists](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/15.JPG)
#
**[Back to The TOP](#section-overview)**

### Doubly Linked Lists in JavaScript

```
class DoublyLinkedList {
    constructor(value) {
      this.head = {
        value: value,
        prev: null,
        next: null,
      };
      this.tail = this.head;
      this.length = 1;
    }
    append(value) {
      const newNode = {
        value: value,
        prev: null,
        next: null,
      };
      newNode.prev = this.tail;
      this.tail.next = newNode;
      this.tail = newNode;
      this.length++;
      return this;
    }
    prepend(value) {
      const newNode = {
        value: value,
        prev: null,
        next: null,
      };
      newNode.next = this.head;
      this.head.prev = newNode;
      this.head = newNode;
      this.length++;
      return this;
    }
    printList() {
      const array = [];
      let currentNode = this.head;
      while (currentNode !== null) {
        array.push(currentNode.value);
        currentNode = currentNode.next;
      }
      return console.log(array);
    }
    insert(index, value) {
      //Check for proper parameters;
      if (index >= this.length) {
        console.log("yes");
        return this.append(value);
      }
  
      const newNode = {
        value: value,
        prev: null,
        next: null,
      };
      const leader = this.traverseToIndex(index - 1);
      const follower = leader.next;
      leader.next = newNode;
      newNode.prev = leader;
      newNode.next = follower;
      follower.prev = newNode;
      this.length++;
      return this.printList();
    }
    traverseToIndex(index) {
      //Check parameters
      let counter = 0;
      let currentNode = this.head;
      while (counter !== index) {
        currentNode = currentNode.next;
        counter++;
      }
      return currentNode;
    }
    remove(index) {
      // Check Parameters
      const leader = this.traverseToIndex(index - 1);
      const unwantedNode = leader.next;
      leader.next = unwantedNode.next;
      this.length--;
      return this.printList();
    }
  }
  
  let myLinkedList = new DoublyLinkedList(10);
  myLinkedList.append(5);
  myLinkedList.append(16);
  myLinkedList.prepend(1);
  myLinkedList.printList();
  myLinkedList.insert(2, 99);
  //   myLinkedList.insert(20, 88);
  //   myLinkedList.remove(2);
```
#
**[Back to The TOP](#section-overview)**

### Singly VS Doubly Linked Lists

Here is a table that summarizes the key differences between singly and doubly linked lists:

| Feature | Singly linked list  | Doubly linked list |
|---------|---------------------|--------------------|
|Direction of traversal| One direction only (forward)|Both directions (forward and backward)|
|Memory usage|Less memory than a doubly linked list|More memory than a singly linked list|
|Efficiency for insertion and deletion|More efficient for insertion and deletion|Less efficient for insertion and deletion|
|Efficiency for operations that require traversing the list in both directions|Less efficient for operations that require traversing the list in both directions|More efficient for operations that require traversing the list in both directions|

Here are some examples of when to use each type of linked list:

**Use a singly linked list when**:
- You only need to traverse the list in one direction.
- Memory is a concern.
- You need to perform frequent insertions and deletions.

**Use a doubly linked list when**:
- You need to traverse the list in both directions.
- You need to perform operations that require traversing the list in both directions.
- You need to be able to quickly access a specific node in the list.
#
**[Back to The TOP](#section-overview)**

### <a name="e-reverse">Exercise: reverse()</a>

```
class LinkedList {
    constructor(value) {
      this.head = {
        value: value,
        next: null,
      };
      this.tail = this.head;
      this.length = 1;
    }
    append(value) {
      const newNode = {
        value: value,
        next: null,
      };
      console.log(newNode);
      this.tail.next = newNode;
      this.tail = newNode;
      this.length++;
      return this;
    }
    prepend(value) {
      const newNode = {
        value: value,
        next: null,
      };
      newNode.next = this.head;
      this.head = newNode;
      this.length++;
      return this;
    }
    printList() {
      const array = [];
      let currentNode = this.head;
      while (currentNode !== null) {
        array.push(currentNode.value);
        currentNode = currentNode.next;
      }
      return console.log(array);
    }
    insert(index, value) {
      //Check for proper parameters;
      if (index >= this.length) {
        console.log("yes");
        return this.append(value);
      }
  
      const newNode = {
        value: value,
        next: null,
      };
      const leader = this.traverseToIndex(index - 1);
      const holdingPointer = leader.next;
      leader.next = newNode;
      newNode.next = holdingPointer;
      this.length++;
      return this.printList();
    }
    traverseToIndex(index) {
      //Check parameters
      let counter = 0;
      let currentNode = this.head;
      while (counter !== index) {
        currentNode = currentNode.next;
        counter++;
      }
      return currentNode;
    }
    remove(index) {
      // Check Parameters
      const leader = this.traverseToIndex(index - 1);
      const unwantedNode = leader.next;
      leader.next = unwantedNode.next;
      this.length--;
      return this.printList();
    }
    reverse() {
      if (!this.head.next) {
        return this.head;
      }
      let first = this.head;
      let second = first.next;
      while (second) {
        const temp = second.next;
        second.next = first;
        first = second;
        second = temp;
      }
      this.head.next = null;
      this.head = first;
      return this.printList();
    }
  }
  
  let myLinkedList = new LinkedList(10);
  myLinkedList.append(5);
  myLinkedList.append(16);
  myLinkedList.prepend(1);
  myLinkedList.printList();
  myLinkedList.insert(2, 99);
  myLinkedList.insert(20, 88);
  myLinkedList.printList();
  myLinkedList.remove(2);
  myLinkedList.reverse();
```
[Core Link](https://github.com/aneagoie/ztm-master-the-coding-interview-ds-algo/blob/main/03_linkedLists/reverseLinkedList.js)

#
**[Back to The TOP](#section-overview)**

### Linked Lists Review

![Linked Lists Review](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/16.JPG)

**[Back to The TOP](#section-overview)**