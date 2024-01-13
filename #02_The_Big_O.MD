<h1 align="center">The Big O</h1>

### Section overview
* **[Setting Up Your Environment](#setting-up-your-environment)**
* **[Big O Cheatsheet](#big-o-cheatsheet)**
* **[What Is Good Code](#what-is-good-code)**
* **[Big O and Scalability](#big-o-and-scalability)**
* **[O(n)](#O(n))**


### Setting Up Your Environment

When it comes to popular online Integrated Development Environments (IDEs), there are several noteworthy options that have gained popularity for their features and ease of use. Let's explore a few of them:

* **[replit](https://replit.com/languages/web_project)**
* **[glot](https://glot.io/)**
* **[jsbin](https://jsbin.com/?html,output)**
* **[Online Python Compiler](https://www.onlinegdb.com/online_python_compiler)**

### Big O Cheatsheet

**Big O notation** is a way to describe the performance or complexity of an algorithm in terms of time and space. 

It provides an upper bound on the growth rate of the function that represents the algorithm's efficiency. 

In simpler terms, it helps us analyze how the runtime or space requirements of an algorithm scale with the input size.

Basic JavaScript forLoop example:

```
const nemo = ['nemo'];

const findNemo = (arr) => {
  for(let i = 0;  i < arr.length; i++){
    if(arr[i] === 'nemo'){
      console.log("Found NEMO!");
    }
  }
};

findNemo(nemo);

// Result in the console: Found NEMO!
```

**[Big O cheatsheet](https://zerotomastery.io/cheatsheets/big-o-cheat-sheet/?utm_source=udemy&utm_medium=coursecontent)** for you as you go through this section and the rest of the course. 

This is a good guide that you can use to remind yourself of some of the key points/tricks when going for an interview. 


### Big O's
* ``O(1)`` Constant - no loops

* ``O(log N)`` Logarithmic - usually searching algorithms have log n if they are sorted (Binary Search)

* ``O(n)`` Linear - for loops, while loops through n items

* ``O(n log(n))`` Log Linear - usually sorting operations

* ``O(n^2)`` Quadratic - every element in a collection needs to be compared to ever other element. Two nested loops

* ``O(2^n)`` Exponential - recursive algorithms that solves a problem of size N

* ``O(n!)`` Factorial - you are adding a loop for every element

Iterating through half a collection is still ``O(n)``

Two separate collections: ``O(a * b)``

| Big O | Name | Description |
| -------- | ------| --------|
| 1 | Constant | statement, one line of code |
| log(n) | Logarithmic | Divide and conquer (binary search) |
| n | Linear | Loop |
| n*log(n) | Linearithmic | Effective sorting algorithms |
| n^2 | Quadratic | Double loop |
| n^3 | Cubic | Triple loop |
| 2^n | Exponential | Complex full search |


### What Can Cause Time in a Function?

* Operations ``(+,-, \*, /)``
* Comparisons ``(<, >, ===)``
* Looping ``(for, while)``
* Outside Function call ``(function())``

### Sorting Algorithms

| Sorting Algorithms | Space complexity | Time complexity | Time complexity |
| -------- | ------| --------| -------- |
|  | Worst case | Best case | Worst case  |
| Insertion Sort | 	O(1) | O(n) | O(n^2)  |
| Selection Sort | 	O(1) | O(n^2) | O(n^2)  |
| Bubble Sort | 	O(1) | O(n) | O(n^2)  |
| Mergesort | 	O(n) | O(n log n) | O(n log n)  |
| Quicksort | 	O(log n) | O(n log n) | O(n^2)  |
| Heapsort | 	O(1) | O(n log n) | O(n log n)  |

### Common Data Structure Operations

| Worst Case→ | Access | Search | Insertion | Deletion | Space Complexity |
| -------- | ------| --------| -------- | -------- | -------- |
| Array | O(1) | O(n) | O(n)  | O(n)  | O(n)  |
| Stack | O(n) | O(n) | O(1)  | O(1)  | O(n)  |
| Queue | O(n) | O(n) | O(1)  | O(1)  | O(n)  |
| Singly-Linked List | O(n) | O(n) | O(1)  | O(1)  | O(n)  |
| Doubly-Linked List | O(n) | O(n) | O(1)  | O(1)  | O(n)  |
| Hash Table | N/A | O(n) | O(n)  | O(n)  | O(n)  |


### Rule Book

**Rule 1:** Always worst Case

**Rule 2:** Remove Constants

**Rule 3:**

- Different inputs should have different variables: ``O(a + b)``.
- A and B arrays nested would be: ``O(a * b)``

(+) for steps in order

(*) for nested steps

**Rule 4:** Drop Non-dominant terms

### What Causes Space Complexity?

* Variables
* Data Structures
* Function Call
* Allocations

**[Back to The TOP](#section-overview)**
#

### What Is Good Code

1. Readable
2. Scalable

**[Back to The TOP](#section-overview)**
#

### Big O and Scalability

**Performance Measurement example**

The time taken to find **'nemo'** in the array is measured, and the result is logged to the console.

```
const nemo = ['nemo'];
const everyone = ['dory', 'bruce', 'marlin', 'nemo', 'gill', 'bloat', 'nigel', 'squirt', 'darla', 'hank'];
const large = new Array(100).fill('nemo');

const findNemo = (arr) =>{
  let t0 = performance.now();
  for(let i = 0; i < arr.length; i++){
   if(arr[i] === 'nemo'){
     console.log("Nemo FOUND!");
   }
  }
  
  let t1 = performance.now();
  const showResult = "Call to find Nemo took " + (t1-t0) + " millseconds";
  console.log(showResult);
}

findNemo(everyone);
```

**[Back to The TOP](#section-overview)**
#

### \O\(\n\)\

#### O(n) - Linear Time
Is a mathematical notation used to describe the growth rate of a function. In computer science, it is used to classify algorithms according to how their run time or space requirements grow as the input size grows.

An algorithm with **O(n)** time complexity means that the algorithm's run time will grow linearly with the input size.


Code example:

```
//ES5
function compressAllBoxes(boxes){
  boxes.forEach(function(item){
      console.log(item);
  });
}

//ES6
const compressAllBoxes = boxes => {
  boxes.forEach(box => console.log(box));
}
```

**[Back to The TOP](#section-overview)**
#







**[Back to The TOP](#section-overview)**
#