<h1 align="center">Algorithms: Recursion</h1>

### Section overview
* **[Introduction to Algorithms](#introduction-to-algorithms)**
* **[Introduction to Recursion](#introduction-to-recursion)**
* **[Anatomy Of Recursion](#anatomy-of-recursion)**
* **[Exercise: Factorial](#e-factorial)**

### Introduction to Algorithms

**What is an Algorithm?**
An algorithm is a set of well-defined instructions that are used to solve a particular problem. An algorithm takes input data, processes it, and produces output data.

Algorithms are important in computer programming because they allow us to tell computers what to do. Without algorithms, computers would be useless.

Data Structures + Algorithms = Programs

``Class{} + function() = Programs`` 

#
**[Back to The TOP](#section-overview)**

### Introduction to Recursion

```
function inception(){
    inception();
}
```
Recursion is a programming concept where a function calls itself in its own definition. It's a powerful technique that allows solving problems in a more concise and elegant way.

Recursion is a powerful tool, but it requires careful design to avoid infinite loops and excessive memory usage.

Here's a recursive JavaScript function to calculate the nth Fibonacci number:
```
function fibonacci(n) {
    // Base cases
    if (n === 0) return 0;
    if (n === 1) return 1;

    // Recursive call
    return fibonacci(n - 1) + fibonacci(n - 2);
}

// Example usage
const result = fibonacci(5);
console.log(result);  // Output: 5
```
#
**[Back to The TOP](#section-overview)**

### Anatomy Of Recursion

**Example when function will return ``undefind``**:

```
let counter = 0;

const inception = () => {

    if(counter > 3){
        return "Done!";
    }

    counter++;
    inception();
};

console.log(inception());
```

**Result in Console**:
```
0
1
2
3
4
undefined
```
**Example when function will return ``Done!``**:
```
let counter = 0;
const inception = () => {

    console.log(counter);

    if(counter > 3){
        return "Done!";
    }

    counter++;
    return inception(); // key factor is return statement
};

console.log(inception());
```
**Result in Console**:
```
0
1
2
3
4
"Done!"
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