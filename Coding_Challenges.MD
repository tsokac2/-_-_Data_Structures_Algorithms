<h1 align="center">Coding Challenges</h1>

### Section overview
* **[Create Rectangles](#create-rectangles)**
* **[Interview Questions: Arrays](#arrays)**
    * **[Two Sum](#two-sum)**
    * **[Maximum Subarray](#maximum-subarray)**
    * **[Move Zeroes](#move-zeroes)**
    * **[Contains Duplicate](#contains-duplicate)**
    * **[Rotate Array](#rotate-array)**
* **[First Recurring Character](#first-recurring)**
* **[Implement Queue using Stacks](#implement-queue-using-stacks)**
* **[Exercise: Factorial](#e-factorial)**
* **[Exercise: Fibonacci](#e-fibonacci)**
* **[Validate Binary Search Tree](#validate-binary-search-tree)**
* **[House Robber](#house-robber)**
* **[Best Time to Buy and Sell Stock](#best-time-to-buy-and-sell-stock)**
* **[Climbing Stairs](#climbing-stairs)**
* **[Coding Problems - Advent of Code](#coding-problems)**

* **[15th Short Challenges](#15th-challenges)**


### Create Rectangles

Given a rectangle with dimensions N*M and an integer K. You divide this rectangle into smaller sub-rectangles such that the given conditions are satisfied:

- Sub-rectangles must be parallel to the axis of the large rectangle with dimensions N*M.
- Every sub-rectangle has at least one edge on the large rectangle edge. Informally, there is no sub-rectangle that is surrounded by other sub-rectangles.

For a sub-rectangle with an area S, the cost of this sub-rectangle is (S - K)^2.

Calculate the minimum total cost to divide the large rectangle into smaller sub-rectangles.

Note: All sub-rectangles must have an integral length of dimensions.

#### Function description

Complete the `solve` function. This function takes the following 3 parameters and returns the required answer:

- `N`: Represents the value of `N`
- `M`: Represents the value of `M`
- `K`: Represents the value of `K`

#### Input format for custom testing

**Note:** Use this input format if you are testing against custom input or writing code in a language where we don't provide boilerplate code.
- The first line contains `T`, which represents the number of test cases.
- For each test case:
    - The first line contains an integer `N`.
    - The second line contains an integer `M`.
    - The third line contains an integer `K`.

#### Output format
For each test case in a new line, print the answer representing the minimum cost.
#
**[Back to The TOP](#section-overview)**

### <a name="arrays">Interview Questions: Arrays</a>
#### Two Sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

**Example 1:**
- **Input**: ``nums = [2,7,11,15], target = 9``
- **Output**: ``[0,1]``
- **Explanation**: ``Because nums[0] + nums[1] == 9, we return [0, 1]``

**Example 2:**

- **Input**: ``nums = [3,2,4], target = 6``
- **Output**: ``[1,2]``

**Example 3:**
- **Input**: ``nums = [3,3], target = 6``
- **Output**: ``[0,1]``

**Constraints:** 
- 2 <= nums.length <= $10^3$
- $10^9$ <= nums[i] <= $10^9$
- $10^9$ <= target <= $10^9$
- **Only one valid answer exists**

**Follow-up**: Can you come up with an algorithm that is less than O(n2) time complexity?

**[Case Link](https://leetcode.com/problems/two-sum/description/)**

**[Back to The TOP](#section-overview)**

#### Maximum Subarray

Given an integer array nums, find the subarray with the largest sum, and return its sum.
A subarray is a contiguous non-empty sequence of elements within an array.

**Example 1**:
- **Input**: ``nums = [-2,1,-3,4,-1,2,1,-5,4]``
- **Output**: ``6``
- **Explanation**: ``The subarray [4,-1,2,1] has the largest sum 6``

**Example 2**:
- **Input**: ``nums = [1]``
- **Output**: ``1``
- **Explanation**: ``The subarray [1] has the largest sum 1``

**Example 3**:
- **Input**: ``nums = [5,4,-1,7,8]``
- **Output**: ``23``
- **Explanation**: ``The subarray [5,4,-1,7,8] has the largest sum 23``

**[Case Link](https://leetcode.com/problems/maximum-subarray/description/)**

**[Back to The TOP](#section-overview)**

#### Move Zeroes
Given an integer array ``nums``, move all ``0``'s to the end of it while maintaining the relative order of the non-zero elements.

**Note** that you must do this in-place without making a copy of the array.

**Example 1**:
- **Input**: ``nums = [0,1,0,3,12]``
- **Output**: ``[1,3,12,0,0]``

**Example 2**:
- **Input**: ``nums = [0]``
- **Output**: ``[0]``

**[Case Link](https://leetcode.com/problems/move-zeroes/description/)**

**[Back to The TOP](#section-overview)**

#### Contains Duplicate
Given an integer array ``nums``, return ``true`` if any value appears **at least twice** in the array, and return false if every element is distinct

**Example 1**:
- **Input**: ``nums = [1,2,3,1]``
- **Output**: ``true``

**Example 2**: 
- **Input**: ``nums = [1,2,3,4]``
- **Output**: ``false``

**Example 3**:
- **Input**: ``nums = [1,1,1,3,3,4,3,2,4,2]``
- **Output**: ``true``

**[Case Link](https://leetcode.com/problems/contains-duplicate/description/)**

**[Back to The TOP](#section-overview)**

#### Rotate Array
Given an integer array ``nums``, rotate the array to the right by ``k`` steps, where ``k`` is non-negative.

**Example 1**:
- **Input**: ``nums = [1,2,3,4,5,6,7], k = 3``
- **Output**: ``[5,6,7,1,2,3,4]``

**Explanation**:
- rotate 1 steps to the right: ``[7,1,2,3,4,5,6]``
- rotate 2 steps to the right: ``[6,7,1,2,3,4,5]``
- rotate 3 steps to the right: ``[5,6,7,1,2,3,4]``

**Example 2**:
- **Input**: ``nums = [-1,-100,3,99], k = 2``
- **Output**: ``[3,99,-1,-100]``

**Explanation**: 
- rotate 1 steps to the right: ``[99,-1,-100,3]``
- rotate 2 steps to the right: ``[3,99,-1,-100]``

**[Case Link](https://leetcode.com/problems/rotate-array/description/)**
#
**[Back to The TOP](#section-overview)**

### First Recurring Character

Goal is to find the first character in a string that occurs more than once. In other words, you're tasked with identifying the first character that appears for the second time in a given sequence of characters.

- ``Given an array = [2,5,1,2,3,5,1,2,4];`` - ``//It should return 2``
- ``Given an array = [2,1,1,2,3,5,1,2,4];`` - ``//It should return 1``
- ``//Given an array = [2,3,4,5];`` - ``//It should return undefined``

#### Solution

```
function firstRecurringCharacter(input) {
  for (let i = 0; i < input.length; i++) {
    for (let j = i + 1; j < input.length; j++) {
      if(input[i] === input[j]) {
        return input[i];
      }
    }
  }
  return undefined
}

function firstRecurringCharacter2(input) {
  let map = {};
  for (let i = 0; i < input.length; i++) {
    if (map[input[i]] !== undefined) {
      return input[i]
    } else {
      map[input[i]] = i;
    }
  }
  return undefined
}

firstRecurringCharacter2([1,5,5,1,3,4,6])


//Bonus... What if we had this:
// [2,5,5,2,3,5,1,2,4]
// return 5 because the pairs are before 2,2
```
#
**[Back to The TOP](#section-overview)**

### Implement Queue using Stacks

Implement a first in first out (FIFO) queue using only two stacks. The implemented queue should support all the functions of a normal queue (``push``, ``peek``, ``pop``, and ``empty``).

Implement the ``MyQueue`` class:

- ``void push(int x)`` Pushes element x to the back of the queue.
- ``int pop()`` Removes the element from the front of the queue and returns it.
- ``int peek()`` Returns the element at the front of the queue.
- ``boolean empty()`` Returns ``true`` if the queue is empty, ``false`` otherwise.

**Notes**:
- You must use **only** standard operations of a stack, which means only ``push to top``, ``peek/pop from top``, ``size``, and ``is empty`` operations are valid.
- Depending on your language, the stack may not be supported natively. You may simulate a stack using a list or deque (double-ended queue) as long as you use only a stack's standard operations.

**Example 1**:

**Input**
```
["MyQueue", "push", "push", "peek", "pop", "empty"]
[[], [1], [2], [], [], []]
```

**Output**
``[null, null, null, 1, 1, false]``

**Explanation**
```
MyQueue myQueue = new MyQueue();
myQueue.push(1); // queue is: [1]
myQueue.push(2); // queue is: [1, 2] (leftmost is front of the queue)
myQueue.peek(); // return 1
myQueue.pop(); // return 1, queue is [2]
myQueue.empty(); // return false
```

#
**[Back to The TOP](#section-overview)**

### <a name="e-factorial">Exercise: Factorial</a>

Write two functions that finds the factorial of any number.

One should use recursive, the other should just use a for loop.

**For loop solution**:
```
function findFactorialIterative(number) {
  let answer = 1;
  // you actually no longer need the if statement because of the for loop
  // if (number === 2) {
  //   answer = 2;
  // }
  for (let i = 2; i <= number; i++) {
    answer = answer * i;
  }
  return answer;
}
findFactorialIterative(5);
```

**Recursive solution**:
```
function findFactorialRecursive(number) {
  if(number === 2) {
    return 2;
  }
  return number * findFactorialRecursive(number - 1)
}
findFactorialRecursive(5);
```
#
**[Back to The TOP](#section-overview)**

### <a name="e-fibonacci"> Exercise: Fibonacci</a>

Given a number N return the index value of the Fibonacci sequence, where the sequence is:

Fibonacci sequence:  0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144 ...

The pattern of the sequence is that each value is the sum of the 2 previous values, that means that for ``N=5 → 2+3``

//For example: fibonacciRecursive(6) should return 8

**For loop solution**:
```
function fibonacciIterative(n){
  let arr = [0, 1];
  for (let i = 2; i < n + 1; i++){
    arr.push(arr[i - 2] + arr[i -1]);
  }
 return arr[n];
}
fibonacciIterative(3);
```

**Recursive solution**:
```
function fibonacciRecursive(n) {
  if (n < 2){
    return n;
  }
  return fibonacciRecursive(n - 1) + fibonacciRecursive (n - 2)
}

fibonacciRecursive(6)
```
#
**[Back to The TOP](#section-overview)**

### Validate Binary Search Tree

Given the root of a binary tree, determine if it is a valid binary search tree (BST).

A **valid BST** is defined as follows:

- The left subtree of a node contains only nodes with keys less than the node's key.
- The right subtree of a node contains only nodes with keys greater than the node's key.
- Both the left and right subtrees must also be binary search trees.

**Example 1**:

![Example_1](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/39.JPG)

- **Input**: ``root = [2,1,3]``
- **Output**: ``true``

**Example 2**:

![Example_2](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/40.JPG)

- **Input**: ``root = [5,1,4,null,null,3,6]``
- **Output**: ``false``
- **Explanation**: ``The root node's value is 5 but its right child's value is 4.``

#
**[Back to The TOP](#section-overview)**

### House Robber

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security systems connected and **it will automatically contact the police if two adjacent houses were broken into on the same night**.

Given an integer array ``nums`` representing the amount of money of each house, return the maximum amount of money you can rob **tonight without alerting the police**.

**Example 1**:
- **Input**: ``nums = [1,2,3,1]``
- **Output**: ``4``
- **Explanation**: ``Rob house 1 (money = 1) and then rob house 3 (money = 3)``.
- Total amount you can rob = 1 + 3 = 4.

**Example 2**:
- **Input**: ``nums = [2,7,9,3,1]``
- **Output**: ``12``
- **Explanation**: Rob house 1 (money = 2), rob house 3 (money = 9) and rob house 5 (money = 1).
- Total amount you can rob = 2 + 9 + 1 = 12.

#
**[Back to The TOP](#section-overview)**

### Best Time to Buy and Sell Stock

You are given an array ``prices`` where ``prices[i]`` is the price of a given stock on the ``i^th`` day.

You want to maximize your profit by choosing a ``single day`` to buy one stock and choosing a ``different day in the future`` to sell that stock.

Return the _maximum profit you can achieve from this transaction_. If you cannot achieve any profit, return 0.

**Example 1**:

- **Input**: ``prices = [7,1,5,3,6,4]``
- **Output**: ``5``
- **Explanation**: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

**Example 2**:
- **Input**: prices = [7,6,4,3,1]
- **Output**: 0
- **Explanation**: In this case, no transactions are done and the max profit = 0.

#
**[Back to The TOP](#section-overview)**

### Climbing Stairs

You are climbing a staircase. It takes ``n`` steps to reach the top.

Each time you can either climb ``1`` or ``2`` steps. In how many distinct ways can you climb to the top?

**Example 1**:
- **Input**: n = 2
- **Output**: 2
- **Explanation**: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps

**Example 2**:
- **Input**: n = 3
- **Output**: 3
- **Explanation**: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step

#
**[Back to The TOP](#section-overview)**


### <a name="coding-problems">Coding Problems - Advent of Code</a>

Advent of Code is an Advent calendar of small programming puzzles for a variety of skill sets and skill levels that can be solved in any programming language you like.

People use them as interview prep, company training, university coursework, practice problems, a speed contest, or to challenge each other.

**[adventofcode](https://adventofcode.com/)**

#
**[Back to The TOP](#section-overview)**

### 15th Challenges

#### Question 1:
What does the fox say?

```
function Fox(color) {
    this.color = color;
}

Fox.prototype.speak = function() {
    console.log("I am " + this.color);
};

var myFox = new Fox("blue");
setTimeout(myFox.speak, 1000);
```
**Answer**:
- [ ] I am red
- [ ] I am blue
- [x] I am undefined
- [ ] Depends on whether this code runs in the browser or on node.js
- [ ] Ring-ding-ding-ding-ding

**Explanation**:
To address this issue and ensure that the speak method is called with the correct ``context``, you should use a function expression in the ``setTimeout`` callback, like this:
```
setTimeout(function() {
    myFox.speak();
}, 1000);
```

#### Question 2:

What is the result of the following statement?

```
let result = [1,2,3].map(v => v + 1).reduce((prev, curr) => prev + curr);
```
**Answer**:
- [ ] Syntax error
- [ ] NaN
- [x] 9 
- [ ] 11

**Explanation**:

- ``map(v => v + 1)``: This part of the code increments each element in the array by ``1``. So, the result of this operation would be ``[2, 3, 4]``.

- ``reduce((prev, curr) => prev + curr)``: This portion of the code uses the reduce function to sum up all the elements in the array. The prev parameter represents the accumulated sum, and ``curr`` represents the current element being processed. In this case, it calculates the sum of all elements in the array. So, for the array ``[2, 3, 4]``, the result would be ``2 + 3 + 4``, which equals ``9``.

#### Question 3:
What does the fox say?

```
class Fox {
    constructor(color) {
        this.color = color
    }
    speak() {
        console.log("I am " + this.color);
    }
}

var myFox = new Fox('blue');
setTimeout(myFox.speak, 1000);
```
**Answer**:
- [ ] I am blue
- [x] I am undefined
- [ ] Depends on whether this code runs in the browser or on node.js
- [ ] Syntax Error

**Explanation**:

The issue with the provided code lies in the way the speak method is invoked using ``setTimeout``. When you pass ``myFox.speak`` as the callback to ``setTimeout``, it loses its context, and when executed, the this inside the speak method will not refer to the ``myFox`` instance. Instead, it will be undefined or refer to the global object (in a browser environment).

To fix this, you can use a callback function with an arrow function to maintain the correct context:
``setTimeout(() => myFox.speak(), 1000);``

#### Question 4:
The following function is what?
```
function sum(a,b){
    console.log(a,b);
    return a + b;
}
```
**Answer**:
- [ ] pure
- [x] determinstic
- [ ] illegal
- [x] synchronous

**Explanation**:

_Pure Function_:

A pure function is a function that always produces the same output for the same input. In other words, a pure function has no side effects and its output depends only on its inputs.
```
function pureSum(a, b) {
  return a + b;
}

console.log(pureSum(1, 2)); // Output: 3
console.log(pureSum(3, 4)); // Output: 7
```

_Deterministic Function_:

A deterministic function is a function that produces the same output for the same input, given the same state. In other words, a deterministic function's output is predictable and depends only on its inputs and the current state of the program.

```
function deterministicSum(a, b) {
  const sum = a + b;
  console.log(sum);
  return sum;
}

console.log(deterministicSum(1, 2)); // Output: 3
console.log(deterministicSum(3, 4)); // Output: 7
```

_Synchronous Function_:

A synchronous function is a function that blocks the execution of the program until it has finished executing. In other words, a synchronous function does not return until it has completed its task.

```
function synchronousSum(a, b) {
  console.log("Calculating sum...");
  const sum = a + b;
  console.log("Sum is:", sum);
  return sum;
}

synchronousSum(2, 3);
console.log("Program continued"); // Output: Calculating sum...
```
#### Question 5:
What will be the console output in JavaScript?

```
(function foo (){
    console.log('foo')
})();

bar();
baz();
foo();

function bar(){
    console.log('bar')
}

const baz = function(){
    console.log('baz')
}
```
**Answer**:

```
foo
bar
```

**Explanation**:
```
(function foo (){
    console.log('foo');
})();
```
- This is an **IIFE (Immediately-Invoked Function Expression)** named ``foo``. 
- The function is defined and immediately invoked. As a result, ``'foo'`` is printed to the console as soon as this code is executed.

```
function bar(){
    console.log('bar');
}
```
- The function bar is declared. 
- Function declarations are hoisted in JavaScript, which means they are moved to the top of their containing scope during the compilation phase. 
- As a result, even though this function is defined later in the code, it is available for invocation throughout the entire scope.

Now, let's summarize the order of execution and console output:

- ``'foo'`` is printed immediately when the IIFE is invoked.
- ``'bar'`` is printed when the function ``bar()`` is called.

Therefore, you see ``'foo'`` and ``'bar'`` in the console output, and this is due to the combination of the IIFE and the hoisting behavior of function declarations in JavaScript.

#### Question 6:
Which of these methods mutate an array in place?

**Answer**:
- [x] push
- [x] pop
- [ ] map
- [x] sort
- [ ] reduce

**Explanation**:

- ``push``: This method does mutate the array by adding elements to its end, thus changing its length. So, [x] push is correct.

- ``pop``: This method also mutates the array by removing the last element, reducing its length. Therefore, [x] pop is correct.

- ``map``: Contrary to the other two, map **does not mutate** the original array. Instead, it creates a new array with the results of calling a provided function on every element. So, [ ] map is not correct in the context of in-place mutation.

- ``sort``: The sort method, as mentioned earlier, mutates the array by rearranging its elements. Thus, [x] sort is correct.

- ``reduce``: Similar to map, the reduce method does not mutate the original array. It reduces the array to a single value based on the provided callback function. Therefore, [ ] reduce is not correct concerning in-place mutation.

#### Question 7:
What will the console output be?

```
function promise() {
    return Promise.reject();
};

promise()
    .then(function () {
        console.log('Then 1');
    })

    .catch(function () {
        console.log('Catch 1')
    })

    .then(function () {
        console.log('Then 2')
    })

    .catch(function () {
        console.log('Catch 2)
    })

    .then(function () {
        console.log('Then 3')
    })
```
**Answer**:
- [ ] Then 1, Catch 1, Then 2, Catch 2, Then 3
- [ ] Then 1, Catch 1

**Explanation**:
- The ``promise()`` function returns a Promise that is rejected.
- The ``.then()`` block following the ``promise()`` is skipped because the promise is rejected. Instead, the control goes to the first ``.catch()`` block.
- The first ``.catch()`` block logs ``'Catch 1'`` to the console.
- The control then goes to the next ``.then()`` block, and it logs ``'Then 2'``.
- Since there's no rejection in the previous step, the following ``.catch()`` block is skipped.
- The last ``.then()`` block logs ``'Then 3'``.

#### Question 8:
In React a pure component is one which...

**Answer**:

- [ ] does not include mixins
- [ ] is a functional component which is also a pure function
- [x] only does a shallow comparison of its props and state
- [ ] does not include other componets
- [ ] does not have state

#### Question 9:
What are some truths about React Hooks?

**Answer**:
- [x]  useEffect combines multiple lifecycle methods into one
- [ ] They work great on class components
- [x] They enable function components to use state
- [ ] Hooks don't work with static typing
- [x] If you only pass one parameter to useEffect, the effect will only run once

#### Question 10:

In React, how would you make sure that some calculated value is not recalculated every time component is rerendered?

**Answer**:
- [x] ``const myVar = React.useMemo(() => {return calculations();}, []);``
- [ ] ``let myVar = null; React.useEffect(() => { myVar = calculations();});``
- [ ] ``let myVar = null; React.useEffect(() => { myVar = calculations();},[])``
- [ ] ``let myVar = null; React.useMemo(() => {myVar = calculations();}, []);``

**Explanation**:

Using useMemo with a dependency array allows you to specify dependencies that, when changed, will trigger the recalculation of the memoized value. 

#### Question 11:
Write a function for adding 2 numbers that are passed in one by one.

**Answer**:
```
function sum(a) {
    // The inner function takes another number and returns the sum
    return function(b) {
        return a + b;
    };
}

// Example usage:
let result = sum(10)(20);
console.log(result);  // Output: 30
```
#### Question 12:
Write a recursive function for summing the yielded values of the following generator:
```
function * gen() {
    for (let i = 0; i < 5; i++) yield i;
}
const myGen  = gen()
```
**Answer**:
```
function * gen() {
    for (let i = 0; i < 5; i++) yield i;
}

const myGen = gen();

function sumGeneratorValues(generator) {
    const { value, done } = generator.next();

    if (done) {
        return 0; // Base case: end of the generator
    } else {
        return value + sumGeneratorValues(generator); // Recursive case: accumulate the value and call the function again
    }
}

const result = sumGeneratorValues(myGen);
console.log(result); // Output: 10 (0 + 1 + 2 + 3 + 4)
```
**Explanation**:

This recursive function, ``sumGeneratorValues``, continues calling itself until it reaches the end of the generator (done is true). It adds up the values during each iteration, resulting in the sum of all yielded values.

**[Back to The TOP](#section-overview)**

