<h1 align="center">Data Structures: Arrays</h1>

### Section overview
* **[Arrays Introduction](#data-structure)**
* **[Static vs Dynamic Arrays](#static-vs-dynamic-arrays)**
* **[Optional: Classes In Javascript](#classes-in-js)**
* **[Implementing An Array](#implementing-an-array)**
* **[Exercise: Reverse A String](#e-reverse-string)**
* **[Exercise: Merge Sorted Arrays](#merge-arrays)**
* **[Arrays: Pros & Cons](#pros-cons)**

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
Arrays in JavaScript are just objects with integer based keys that act like indexes.

#### How to build one with ``class`` in JavaScript and how to use it

```
class MyArray {
    constructor(){
        this.length = 0;
        this.data = {}
    }

    get(index) {
        return this.data[index]
    }

    push(item) {
        this.data[this.length] = item;
        this.length++
        return this.length;
    }

    pop(){
        const lastItem = this.data[this.length-1];
        delete this.data[this.length-1];
        this.length--;
        return lastItem;
    }

    delete(index) {
        const item = this.data[index];
        this.shiftItems(index);
        return lastItem;
    }

    shiftItems(index) {
        for(let i = index; i < this.length - 1; i++){
            this.data[i] = this.data[i+1];
        }
        delete this.data[this.length-1];
        this.length--;
    }
}

const newArray = new MyArray();
newArray.push('hi');
newArray.puhs('you');
newArray.puhs('!');
newArray.pop();
newArray.delete(0);
newArray.push('are');
newArray.push('nice');
newArray.delete(1);
console.log(newArray.get(0));
```

**[Back to The TOP](#section-overview)**
#

### Strings and Arrays
Common interview trick is where you're manipulating strings.

Do some sort of a loop on it or an operation using something like a ``split method`` in JavaScript and then returning it as a string after you've finished the operations with them.

![Strings and Arrays](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/07.JPG)

**[Back to The TOP](#section-overview)**
#

### <a name="e-reverse-string">Exercise: Reverse A String</a>
Create a function that reverses a string: ``"Hi My Name is Tomislav"``, should be ``""valsimoT si emaN yM iH""``

**Solutions':**

1. Solution:

```
const string = "Hi My Name is Tomislav";

const reverse1 = str => {
  if(!str || str.length < 2 || typeof str !== "string"){
    return "Invalid input";
  }

  let backwards = []
  let totalItems = str.length - 1;  // The total number of characters in the input string minus one (to get the last index).
  for(let i = totalItems; i >= 0; i--){
    backwards.push(str[i]);
  }
  return backwards.join('');

};

console.log(reverse1(string));

// "valsimoT si emaN yM iH"
```

2. Solution:

```
const string = "Hi My Name is Tomislav";

const reverse2 = str => {
  if(!str || str.length < 2 || typeof str !== "string"){
    return "Invalid input!";
  }
  
  return str.split('').reverse().join('');
};

//"valsimoT si emaN yM iH"
```

3. Solution:
```
const string = "Hi My Name is Tomislav";

const reverse3 = str => str.split('').reverse().join('');

console.log(reverse3(string));

//"valsimoT si emaN yM iH"
```

4. Solution:
```
const string = "Hi My Name is Tomislav";

const reverse4 = str => [...str].reverse().join('');

console.log(reverse4(string));

//"valsimoT si emaN yM iH"
```
**[Back to The TOP](#section-overview)**
#

### <a name="merge-arrays">Exercise: Merge Sorted Arrays </a>

Given two arrays that are sorted. Merge these two arrays into one array that's is sorted.

**Solution**
```
function mergeSortedArrays(array1, array2){
  const mergedArray = [];
  let array1Item = array1[0];
  let array2Item = array2[0];
  let i = 1;
  let j = 1;
  
  //We should actually move these 2 if statements to line 2 so that we do the checks before we do assignments in line 3 and 4!
  if(array1.length === 0) {
    return array2;
  }
  if(array2.length === 0) {
    return array1;
  }

  while (array1Item || array2Item){
   if(array2Item === undefined || array1Item < array2Item){
     mergedArray.push(array1Item);
     array1Item = array1[i];
     i++;
   }   
   else {
     mergedArray.push(array2Item);
     array2Item = array2[j];
     j++;
   }
  }
  return mergedArray;
}

mergeSortedArrays([0,3,4,31], [3,4,6,30]);
```
**[Back to The TOP](#section-overview)**

### <a name="pros-cons">Arrays: Pros & Cons</a>

![Array-Pros-Cons](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/08.png)

**[Back to The TOP](#section-overview)**