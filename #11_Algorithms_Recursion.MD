<h1 align="center">Algorithms: Recursion</h1>

### Section overview
* **[Introduction to Algorithms](#introduction-to-algorithms)**
* **[Introduction to Recursion](#introduction-to-recursion)**
* **[Anatomy Of Recursion](#anatomy-of-recursion)**


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

#
**[Back to The TOP](#section-overview)**