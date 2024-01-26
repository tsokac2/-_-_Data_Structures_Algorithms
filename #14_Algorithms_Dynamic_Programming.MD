<h1 align="center">Algorithms: Dynamic Programming</h1>

### Section overview
* **[Dynamic Programming Introduction](#dynamic-programming-introduction)**
* **[Memoization 1](#memoization)**


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