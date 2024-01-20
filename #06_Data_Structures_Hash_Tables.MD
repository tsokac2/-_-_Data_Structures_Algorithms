<h1 align="center">Data Structures: Hash Tables</h1>

### Section overview
* **[Arrays Introduction](#data-structure)**
* **[Hash Function](#hash-function)**
* **[Map() & Set() in JavaScript](#map-set)**



### Arrays Introduction
- In ``JavaScript``, hash tables are commonly referred to as ``"objects"`` or "associative arrays."
- In ``Python``, hash tables are implemented using a built-in data type called a ``"dictionary."``
- In ``Java``, the equivalent of hash tables is provided by the ``HashMap class``, which is part of the Java Collections Framework. 
- In ``Ruby``, hash tables are typically referred to as ``"Hash"`` or ``"Hashes."``

![Hash Tables](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/09.JPG)

**[Back to The TOP](#section-overview)**

### Hash Function

A Hash Function is a mathematical function that takes data of any size and produces a fixed-size output. This output is called a hash value, hash code, digest, or simply a hash. 

Hash functions are used in a variety of applications, including:

- **Data storage and retrieval**: Hash functions are used to index data in hash tables, which are a type of data structure that allows for fast and efficient searching and retrieval of data.
- **File integrity checking**: Hash functions can be used to create digital signatures that can be used to verify that a file has not been tampered with.
- **Password storage**: Hash functions can be used to store passwords securely without storing the actual password text.

#
**[Back to The TOP](#section-overview)**

### Hash Collisions

![Hash Tables](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/10.JPG)

#### Object in JavaScript
```
const user = {
  age: 54,
  name: 'Keyli',
  magic: true,
  speak: ()=>{console.log("Yeah budeeee!")}
}

console.log(user.age);  //54
console.log(user.name); //"Keyli"
user.speak(); // "Yeah budeeee!"
```

#### Collisions in the memory

![Hash Tables](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/11.JPG)

#
**[Back to The TOP](#section-overview)**

### <a name="map-set">Map() & Set() in JavaScript</a>

#### Map
A Map is an object-like collection that stores key-value pairs. Each key in a Map is unique, and it corresponds to a single value. And another benefit of map is that it maintains insertion order.

Creating a Map is straightforward using the new ``Map()`` constructor:

``const myMap = new Map();``

To add key-value pairs to a Map, use the ``set()`` method:
```
myMap.set('name', 'Bard');
myMap.set('age', 3);
```

Retrieving values from a Map using a key is done with the get() method:
```
const name = myMap.get('name'); // name will be 'Bard'
const age = myMap.get('age'); // age will be 3
```

#### Set
A Set is an unordered collection of unique values. Unlike Maps, Sets don't have keys; they simply store distinct elements. This property makes Sets ideal for maintaining collections where duplicate values are not allowed and the order of elements is not important.

Creating a Set using the new Set() constructor:
``const mySet = new Set();``

Adding elements to a Set using the add() method:

#### Applications of Maps and Sets
```
mySet.add(10);
mySet.add('Hello');
mySet.add('World');
```

Maps and Sets find their applications in various scenarios, including:

- Storing user preferences and data associated with unique identifiers
- Maintaining a list of distinct items without duplicate entries
- Performing operations like finding the frequency of elements or identifying unique combinations of items

#
**[Back to The TOP](#section-overview)**