<h1 align="center">Data Structures: Arrays</h1>

### Section overview
* **[Arrays Introduction](#data-structure)**
* **[Static vs Dynamic Arrays](#static-vs-dynamic-arrays)**
* **[Optional: Classes In Javascript](#classes-in-js)**
* **[Implementing An Array](#implementing-an-array)**



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

![Objects](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/06.png)

Three things that are importnat with objects:

#### Reference Type (Object):
Objects are instances of reference types in JavaScript. They are complex data types that can hold key-value pairs and methods, making them versatile for representing real-world entities.

```
[] === []; //false
[1] === [1] //false

var obect1 = { value: 10};
var object2 = object1;
var object3 = {value:10};

object1 === object2 //true
object1 === object3 //false
```

#### Scope
Scope refers to the visibility and accessibility of variables in different parts of your code.

**Global Scope**: Variables declared outside any function or block have a global scope. They can be accessed from any part of the code.
```
let globalVar = "I am global";

function exampleFunction() {
  console.log(globalVar); // Accessible
}
```

**Local Scope**: Variables declared within a function have a local scope. They are only accessible within that function.
```
function exampleFunction() {
  let localVar = "I am local";
  console.log(localVar); // Accessible
}

console.log(localVar); // Not accessible
```
#### Context
Context tells you where we are within the object.

Context refers to the value of the ``this`` keyword within a particular execution context.

``this`` - What is the object environment that we're in right now?

**Global Context**: When this is used outside of any function or object, it refers to the global object (e.g., window in browsers).
```
console.log(this); // Points to the global object (e.g., window)
```
However, if the function is part of an object, this refers to that object.

```
let obj = {
  prop: "I am an object property",
  logProp: function() {
    console.log(this.prop);
  }
};

obj.logProp(); // Points to the 'obj' object
```

#### Instantiation
Instantiation is when you make a copy of an object and reuse the code. You're making instances or multiple copies of an object.

Now think of a ``class`` as something that I want to make a copy of.

```
class Player {
    constructor(name, type){
        this.name = name;
        this.type = type;
    }

    introduce() {
        console.log(`Hi I am ${this.name}, I'm a ${this.type}`)
    }
}

class Wizard extends Player {
    constructor(name, type) {
        super(name, type)
    }

    play() {
        console.log(`WEEEEEE I'm a ${this.type}`);
    }
}

const wizard1 = new Wizard("Shelly", "Healer");
const wizard2 = new Wizard("Shawn", "Dark Magic");
```

**[Back to The TOP](#section-overview)**
#

### Implementing An Array



**[Back to The TOP](#section-overview)**
#