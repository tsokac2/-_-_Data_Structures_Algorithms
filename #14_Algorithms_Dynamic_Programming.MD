<h1 align="center">Algorithms: Dynamic Programming</h1>

### Section overview
* **[Dynamic Programming Introduction](#dynamic-programming-introduction)**
* **[Memoization](#memoization)**
* **[Dynamic Programming Rules](#dynamic-programming-rules)**
* **[Implementing Dynamic Programming](#implementing-dynamic-programming)**


### Dynamic Programming Introduction

Dynamic programming (DP) is a mathematical optimization method and computer programming technique for solving complex problems by breaking them down into smaller subproblems.

#
### Memoization 

In computing, memoization or memoisation is an optimization technique used primarily to speed up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again. 

This is achieved by keeping a cache of previously calculated results, which can be accessed and reused whenever the same input is encountered again.

```
//learn to cache
function addTo80(n) {
    return n + 80;
  }
  
  addTo80(5)
  
  let cache = {};
  function memoizeAddTo80(n) {
    if (n in cache) {
      return cache[n];
    } else {
      console.log('long time');
      const answer = n + 80;
      cache[n] = answer;
      return answer;
    }
  }
  
  // console.log(1, memoizeAddTo80(6))
  // // console.log(cache)
  // // console.log('-----------')
  // console.log(2, memoizeAddTo80(6))
  
  // let's make that better with no global scope. This is closure in javascript so.
  function memoizeAddTo80(n) { 
    let cache = {};
    return function(n) {
      if (n in cache) {
        return cache[n];
      } else {
        console.log('long time');
        const answer = n + 80;
        cache[n] = answer;
        return answer;
      }
    }
  }
  
  const memoized = memoizeAddTo80();
  console.log(1, memoized(6))
  // console.log(cache)
  // console.log('-----------')
  console.log(2, memoized(6))
```
#
**[Back to The TOP](#section-overview)**

### Fibonacci and Dynamic Programming

**JavaScript Example**:

```
//0,1,1,2,3,5,8,13,21,34,55,89,144,233

let calculations = 0;
const fibonacci = n => {
    calculations++;
    console.log(calculations)
    if(n < 2){
        return n;
    }
    return fibonacci(n-1) + fibonacci(n-2);
};
fibonacci(6);

//Return 25 calculations for n = 6 - not very efficiant
```
#
**[Back to The TOP](#section-overview)**

### Dynamic Programming Rules

![Dynamic Programing Rules](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/41.png)

![Dynamic Programing Rules](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/42.png)

#
**[Back to The TOP](#section-overview)**

### Implementing Dynamic Programming

**JavaScript code example**:

```
//0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233...
let calculations = 0;
function fibonacci(n) {
  //O(2^n)

  if (n < 2) {
    return n;
  }
  return fibonacci(n - 1) + fibonacci(n - 2);
}

function fibonacciMaster() {
  //O(n)
  let cache = {};
  return function fib(n) {
    calculations++;
    if (n in cache) {
      return cache[n];
    } else {
      if (n < 2) {
        return n;
      } else {
        cache[n] = fib(n - 1) + fib(n - 2);
        return cache[n];
      }
    }
  };
}

function fibonacciMaster2(n) {
  let answer = [0, 1];
  for (let i = 2; i <= n; i++) {
    answer.push(answer[i - 2] + answer[i - 1]);
  }
  return answer.pop();
}

const fasterFib = fibonacciMaster();

console.log("Slow", fibonacci(35));
console.log("DP", fasterFib(100));
console.log("DP2", fibonacciMaster2(100));
console.log("we did " + calculations + " calculations");
```
#
**[Back to The TOP](#section-overview)**

###  Dynamic Programming Review


#
**[Back to The TOP](#section-overview)**