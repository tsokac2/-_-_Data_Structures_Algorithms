<h1 align="center">Data Structures: Arrays</h1>

### Section overview
* **[Arrays Introduction](#data-structure)**
* **[Static vs Dynamic Arrays](#static-vs-dynamic-arrays)**
* **[Optional: Classes In Javascript](#classes-in-js)**


### Arrays Introduction
Arrays which are sometimes called lists. Organizes items sequentially.

![Arrays](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/05.JPG)

```
const strings = ["a","b","c","d"];

//push method
strings.push("e"); //O(1) Big O Constant

//pop
strings.pop();
strings.pop(); //O(1) - Big O Constant 

//unshift
strings.unshift("x"); //O(n)

//splice
strings.splice(2, 0, "alien"); //O(n)
```
**[Back to The TOP](#section-overview)**
#

### Static vs Dynamic Arrays

#### Static Arrays
- Static arrays have a **fixed size**, meaning that you need to declare the size of the array before compiling your code.
- This can be advantageous in terms of memory management and simplicity, especially when the size of the data is known in advance.

#### Dynamic Arrays
- Dynamic arrays, on the other hand, allow you to change the size of the array **during runtime**.
- This flexibility is beneficial when dealing with data structures that may grow or shrink based on user input or other dynamic factors.

**[Back to The TOP](#section-overview)**
#

### <a name="classes-in-js">Optional: Classes In Javascript</a>



**[Back to The TOP](#section-overview)**
#
