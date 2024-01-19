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

**[Back to The TOP](#section-overview)**



