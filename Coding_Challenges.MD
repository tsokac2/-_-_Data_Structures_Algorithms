<h1 align="center">Coding Challenges</h1>

### Section overview
* **[Create Rectangles](#create-rectangles)**
* **[15th Challenges](#15th-challenges)**


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


### Two Sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists



