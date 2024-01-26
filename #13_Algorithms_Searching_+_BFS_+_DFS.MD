<h1 align="center">#13_Algorithms_Searching_+_BFS + DFS</h1>

### Section overview

* **[Linear Search](#linear-search)**
* **[Binary Search](#binary-search)**

### Linear Search
A linear search, also known as a sequential search, is a simple method for finding a specific value within a list or array. 

In this search algorithm, each element in the list is checked one by one until the desired item is found or the entire list has been traversed.

```
const beasts = ["Centaur", "Godzilla", "Mosura", "Minotaur", "Hydra", "Nessie"];

beasts.indexOf("Godzilla");
// Returns: 1

beasts.findIndex((item) => {
    return item === "Godzilla";
});
// Returns: 1

beasts.find((item) => {
    return item === "Godzilla";
});
// Returns: "Godzilla"

beasts.includes("Godzilla");
// Returns: true
```
#
**[Back to The TOP](#section-overview)**

### Binary Search

You split a list of a sorted item and decide from there whether item you're looking for is in the left or the right of the list.

![Binary Search]()

#
**[Back to The TOP](#section-overview)**