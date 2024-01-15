<h1 align="center">The Big O</h1>

### Section overview
* **[Setting Up Your Environment](#setting-up-your-environment)**
* **[Big O Cheatsheet](#big-o-cheatsheet)**
* **[What Is Good Code](#what-is-good-code)**
* **[Big O and Scalability](#big-o-and-scalability)**
* **[O(n)](#o-n)**
* **[O(1)](#o-1)**
* **[Exercise: Big O Calculation](#big-o-e)**
* **[Simplifying Big O](#simplifying-big-o)**
* **[Big O Rule 1 - Worst Case](#rule-1)**
* **[Big O Rule 2 - Remove Constants](#rule-2)**
* **[Big O Rule 3 - Different terms for inputs](#rule-3)**
* **[Big O Rule 4 - Drop Non Dominants](#rule-4)**
* **[Big O Cheat-Sheet](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/BigO-cheat-sheet.pdf)**
* **[3 Pillars Of Programming](#3-pillars-of-programming)**

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

### <a name="o-n">O(n)</a>
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

### <a name="o-1">O(1)</a>
#### O(1) - Constant Time

**O(1)** denotes constant time complexity, meaning that the algorithm's execution time does not depend on the size of the input. 

Regardless of how large the dataset becomes, the algorithm's performance remains constant.

**[Back to The TOP](#section-overview)**
#

### <a name="big-o-e">Exercise: Big O Calculation</a>

#### 1. What is the Big O of the below function? (Hint, you may want to go line by line)
```
function funChallenge(input) {
  let a = 10;
  a = 50 + 3;

  for (let i = 0; i < input.length; i++) {
    anotherFunction();
    let stranger = true;
    a++;
  }
  return a;
}
```
**Big O = 3 + 4n = O(n)**

#### 2. What is the Big O of the below function? (Hint, you may want to go line by line)
```
function anotherFunChallenge(input) {
    let a = 5; // O(1)
    let b = 10; // O(1)
    let c = 50; // O(1)
    for (let i = 0; i < input; i++) { // O(n)
      let x = i + 1; // O(n)
      let y = i + 2; // O(n)
      let z = i + 3; // O(n)

    }
    for (let j = 0; j < input; j++) { // O(n)
      let p = j * 2; // O(n)
      let q = j * 2; // O(n) 
    }
    let whoAmI = "I don't know"; // O(1)
  }
```
**Big O = 4 + 7n = O(n)**

**[Back to The TOP](#section-overview)**
#

### Simplifying Big O

- **Rule 1**: Worst Case
- **Rule 2**: Remove Constants
- **Rule 3**: Different terms for inputs
- **Rule 4**: Drop Non Dominants

#
### <a name="rule-1">Big O Rule 1 - Worst Case</a>

For a given algorithm, the **worst-case** time complexity is the maximum amount of time it **could** take to complete when given a particular input. 

It is a measure of the algorithm's efficiency when dealing with the least favorable input.

Code example:
```
const nemo = ['nemo'];
const everyone = ['dory', 'bruce', 'marlin', 'nemo', 'gill', 'bloat', 'nigel', 'squirt', 'darla', 'hank'];

const findNemo = (arr) =>{
  for(let i = 0; i < arr.length; i++){
    console.log(arr[i]);
   if(arr[i] === 'nemo'){
     console.log("Nemo FOUND!");
     break;
   }
  }
}

findNemo(everyone);
```
Result in the console:

```
"dory"
"bruce"
"marlin"
"nemo"
"Nemo FOUND!"
```
The time complexity of this algorithm in the worst-case scenario is O(n), where 'n' is the size of the input array. This is because, in the worst case, the function needs to traverse the entire list to find the  ``nemo`` element.

With the ``break;`` we can shorten traverse time. 

**[Back to The TOP](#section-overview)**
#

### <a name="rule-2">Big O Rule 2 - Remove Constants</a>

When we discuss the time complexity using Big O notation, we focus on the **growth rate** of the algorithm as the input size increases. 

``Rule 2`` suggests that we should disregard constant factors when expressing the time complexity. 

In other words, if an algorithm has a time complexity of O(2n) or O(5n), we simplify it to ``O(n)``, as the constant factor (2 or 5) doesn't impact the overall growth rate as significantly as the input size.

Code Example:

```
function cimpressBoxesTwice(boxes){
  boxes.forEach(function(boxes){
    console.log(boxes);
  });

  boxes.forEach(function(boxes){
    console.log(boxes);
  });
}
```
It this example - **``O(2n)`` we can Drop the Constants and simply say - ``O(n)``**

**[Back to The TOP](#section-overview)**
#

### <a name="rule-3">Big O Rule 3 - Different terms for inputs</a>

**Rule of thumb** - when you see nested loops, the Big O is:  ``O(n^2)``.

Code Example:
```
const boxes = [1,2,3,4,5];

const logAllPairsOfArray = (arr) => {
  for(let i = 0; i < arr.length; i++){
    for(let j = 0; j < arr.length; j++){ // nested for loop
      console.log(arr[i]+ ' : '+ arr[j]);
    }
  }
};

logAllPairsOfArray(boxes);
```
#### ``0(a*b)`` 
Where ``a`` and ``b`` represents two different inputs with different lengths but they are nested.

Code Example:
```
const box_a = [1,2,3,4,5];
const box_b = [2,3];

function cimpressBoxesTwice(a, b){
  a.forEach(function(boxes){
    console.log(boxes);

      b.forEach(function(boxes){
      console.log(boxes);
    });
  });
}
cimpressBoxesTwice(box_a, box_b);
```
**[Back to The TOP](#section-overview)**
#

### <a name="rule-4">Big O Rule 4 - Drop Non Dominants</a>

Big O example: ``O(x^2+3x+100+x/2)`` - if a ``x = 500``, then ``x^2`` will became a dominat. In this case we can drop all **Non** dominants, where the Big O will be - ``O)x^2)``.

**"Drop Non-Dominants,"** deals with simplifying the expression for the time complexity of an algorithm by removing ``less significant`` terms and constants.

Now, let's say we have another piece of code that has an additional constant factor:

```
function anotherFunction(arr) {
  // Constant time operation
  console.log(arr[0]);

  // Outer loop
  for (let i = 0; i < arr.length; i++) {
    // Inner loop
    for (let j = 0; j < arr.length; j++) {
      console.log(arr[i], arr[j]);
    }
  }
}
```

Even though we have added a constant time operation ``(console.log(arr[0]))``, when analyzing the time complexity, we still focus on the dominant term, which is the nested loops. Therefore, the overall time complexity remains ``O(n^2)``.

**[Back to The TOP](#section-overview)**
#

### 3 Pillars Of Programming

1. Readable
2. Scalable
  - Speed - Time Complexity
  - Memory - Space Complexity

#### Space complexity

Space complexity in programming is a measure of the amount of memory an algorithm or program uses in relation to the size of its input. 

It is a crucial aspect of algorithm analysis, as it determines the resources required to run the algorithm efficiently. 

Just as time complexity characterizes the computational effort, space complexity quantifies the memory overhead.

By understanding space complexity, programmers can make informed decisions about algorithm selection and implementation to optimize resource usage and achieve efficient program performance.

Code examples:
```
const booooo = (n) => {
  for (let i = 0; i < n; i++){
    console.log("Boooo!")
  }
};

booooo(6); //O(1) of Space complexity

// 
const arrayOfHiNTimes = (n) => {
  let hiArray = [];
  for (let i = 0; i < n; i++) {
    console.log(hiArray[i] = "hi");
  }
  return hiArray;
}
arrayOfHiNTimes(6); //O(n) Space complexity sice we are ading n items in to hiArray array
```
**[Back to The TOP](#section-overview)**
#