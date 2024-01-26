<h1 align="center">#13_Algorithms_Searching_+_BFS + DFS</h1>

### Section overview
* **[Linear Search](#linear-search)**
* **[Binary Search](#binary-search)**
* **[BFS (Breadth First Search) Introduction](#bfs)**
* **[DFS (Depth First Search) Introduction](#dfs)**

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

**Initial Setup**:
- Begin with the entire sorted collection.
- Identify the middle element.

**Comparison**:
- Compare the middle element with the target value you are searching for.

**Adjusting Search Range**:
- If the middle element is equal to the target, the search is successful, and the index is returned.
- If the middle element is greater than the target, narrow the search to the lower half.
- If the middle element is less than the target, narrow the search to the upper half.

**Repeat**:
- Repeat steps 2 and 3 until the target value is found or the search range is empty.

**Outcome**:
- If the target is found, return its index.
- If the search range becomes empty, the target is not in the collection.

![Binary Search](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/36.JPG)

#
**[Back to The TOP](#section-overview)**

### <a name="bfs">BFS (Breadth First Search) Introduction</>

Breadth-First Search (BFS) is a graph traversal algorithm used to explore all the vertices of a graph in breadthward motion. 
 
The main idea behind BFS is to visit all the neighbors of a given node before moving on to the next level of nodes in the graph.

#
**[Back to The TOP](#section-overview)**

### <a name="dfs">DFS (Depth First Search) Introduction</>

Depth First Search (DFS) is a graph traversal algorithm that explores as far as possible along each branch before backtracking. 

It's a fundamental algorithm used in graph theory and various applications, including maze solving, topological sorting, and connected components identification.

#
**[Back to The TOP](#section-overview)**