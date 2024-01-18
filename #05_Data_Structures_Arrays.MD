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

In JavaScript, data types can be broadly categorized into two main groups: **primitive** and **non-primitive (or reference)** types.

#### Primitive Data Types:

- **String**: Used to represent textual data. Enclosed in single or double quotes.
- **Number**: Represents numeric values, both integers and floating-point numbers.
- **Boolean**: Represents true or false values.
- **Undefined**: Represents a variable that has been declared but not assigned a value.
- **Null**: Represents the intentional absence of any object value.
Symbol**: Introduced in ECMAScript 6, symbols are unique and immutable primitive values.

#### Non-Primitive (Reference) Data Types:

- **Object**: A complex data type that can hold key-value pairs and methods. Objects are used to represent real-world entities.
- **Array**: An ordered collection of values, where each value can be of any data type.
- **Function**: A reusable block of code that can be invoked by its name. Functions are a subtype of objects.
- **Date**: Represents dates and times.
- **RegExp**: Represents regular expressions for pattern matching.



Three things that are importnat with objects:

//reference type

[] === []; //false
[1] === [1] //false

var obect1 = { value: 10};
var object2 = object1;
var object3 = {value:10};

object1 === object2 //true
object1 === object3 //false




//context
//instantiation



![Objects](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/06.png)

**[Back to The TOP](#section-overview)**
#
