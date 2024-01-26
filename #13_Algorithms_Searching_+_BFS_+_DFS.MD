<h1 align="center">Algorithms: Searching + BFS + DFS</h1>

### Section overview
* **[Linear Search](#linear-search)**
* **[Binary Search](#binary-search)**
* **[BFS (Breadth First Search) Introduction](#bfs)**
* **[DFS (Depth First Search) Introduction](#dfs)**
* **[BFS vs DFS](#bfs-vs-dfs)**
* **[Exercise: BFS vs DFS](#e-bfs-vs-df)**
* **[breadthFirstSearch()](#code-bfs)**
* **[depthFirstSearch()](#code-dfs)**
* **[Dijkstra + Bellman-Ford Algorithms](#d-b)**
* **[Big O - BFS and DFS](https://stackoverflow.com/questions/9844193/what-is-the-time-and-space-complexity-of-a-breadth-first-and-depth-first-tree-tr)**


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

**Logic Example**:

```
//     9
//  4     20
//1  6  15  170
```
**Array example**: ``[9, 4, 20, 1, 6, 15, 170]``
#
**[Back to The TOP](#section-overview)**

### <a name="dfs">DFS (Depth First Search) Introduction</>

Depth First Search (DFS) is a graph traversal algorithm that explores as far as possible along each branch before backtracking. 

It's a fundamental algorithm used in graph theory and various applications, including maze solving, topological sorting, and connected components identification.

**Logic Example**:

```
//     9
//  4     20
//1  6  15  170
```
**Array example**: ``[9, 4, 20, 1, 6, 20, 15, 170]``

#
**[Back to The TOP](#section-overview)**

### BFS vs DFS

In choosing between BFS and DFS, the specific requirements of the problem and the characteristics of the graph play a crucial role. 

If you need the shortest path, BFS is often preferable. 

If memory is a concern or you're dealing with a deep graph, DFS might be a better choice.

#### BFS

![BFS](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/37.JPG)

#### DFS

![DFS](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/38.JPG)

#
**[Back to The TOP](#section-overview)**

### <a name="e-bfs-vs-dfs" >Exercise: BFS vs DFS</a>

1. If you know a solution is not far from the root of the tree: **BFS**
2. If the tree is very deep and solutions are rare: **BFS (DFS will take long)**
3. If the tree is very wide: **DFS (BFS will need to much memory)**
4. If solutions are frequent but located deep in the tree: **DFS**
5. Determining whether a path exists between two nodes: **DFS**
6. Finding the shortest path: **BFS**

#
**[Back to The TOP](#section-overview)**

<a name="code-bfs">breadthFirstSearch()</a>

**JavaScript Example**:
```
class Node {
    constructor(value) {
      this.left = null;
      this.right = null;
      this.value = value;
    }
  }
  
  class BinarySearchTree {
    constructor() {
      this.root = null;
    }
    insert(value) {
      const newNode = new Node(value);
      if (this.root === null) {
        this.root = newNode;
      } else {
        let currentNode = this.root;
        while (true) {
          if (value < currentNode.value) {
            //Left
            if (!currentNode.left) {
              currentNode.left = newNode;
              return this;
            }
            currentNode = currentNode.left;
          } else {
            //Right
            if (!currentNode.right) {
              currentNode.right = newNode;
              return this;
            }
            currentNode = currentNode.right;
          }
        }
      }
    }
    lookup(value) {
      if (!this.root) {
        return false;
      }
      let currentNode = this.root;
      while (currentNode) {
        if (value < currentNode.value) {
          currentNode = currentNode.left;
        } else if (value > currentNode.value) {
          currentNode = currentNode.right;
        } else if (currentNode.value === value) {
          return currentNode;
        }
      }
      return null;
    }
    remove(value) {
      if (!this.root) {
        return false;
      }
      let currentNode = this.root;
      let parentNode = null;
      while (currentNode) {
        if (value < currentNode.value) {
          parentNode = currentNode;
          currentNode = currentNode.left;
        } else if (value > currentNode.value) {
          parentNode = currentNode;
          currentNode = currentNode.right;
        } else if (currentNode.value === value) {
          //We have a match, get to work!
  
          //Option 1: No right child:
          if (currentNode.right === null) {
            if (parentNode === null) {
              this.root = currentNode.left;
            } else {
              //if parent > current value, make current left child a child of parent
              if (currentNode.value < parentNode.value) {
                parentNode.left = currentNode.left;
  
                //if parent < current value, make left child a right child of parent
              } else if (currentNode.value > parentNode.value) {
                parentNode.right = currentNode.left;
              }
            }
  
            //Option 2: Right child which doesnt have a left child
          } else if (currentNode.right.left === null) {
            currentNode.right.left = currentNode.left;
            if (parentNode === null) {
              this.root = currentNode.right;
            } else {
              //if parent > current, make right child of the left the parent
              if (currentNode.value < parentNode.value) {
                parentNode.left = currentNode.right;
  
                //if parent < current, make right child a right child of the parent
              } else if (currentNode.value > parentNode.value) {
                parentNode.right = currentNode.right;
              }
            }
  
            //Option 3: Right child that has a left child
          } else {
            //find the Right child's left most child
            let leftmost = currentNode.right.left;
            let leftmostParent = currentNode.right;
            while (leftmost.left !== null) {
              leftmostParent = leftmost;
              leftmost = leftmost.left;
            }
  
            //Parent's left subtree is now leftmost's right subtree
            leftmostParent.left = leftmost.right;
            leftmost.left = currentNode.left;
            leftmost.right = currentNode.right;
  
            if (parentNode === null) {
              this.root = leftmost;
            } else {
              if (currentNode.value < parentNode.value) {
                parentNode.left = leftmost;
              } else if (currentNode.value > parentNode.value) {
                parentNode.right = leftmost;
              }
            }
          }
          return true;
        }
      }
    }
    breadthFirstSearch() {
      let currentNode = this.root;
      let list = [];
      let queue = [];
      queue.push(currentNode);
  
      while (queue.length > 0) {
        currentNode = queue.shift();
        console.log(currentNode.value);
        list.push(currentNode.value);
        if (currentNode.left) {
          queue.push(currentNode.left);
        }
        if (currentNode.right) {
          queue.push(currentNode.right);
        }
      }
    }
  }
  
  const tree = new BinarySearchTree();
  tree.insert(9);
  tree.insert(4);
  tree.insert(6);
  tree.insert(20);
  tree.insert(170);
  tree.insert(15);
  tree.insert(1);
  tree.remove(170);
  JSON.stringify(traverse(tree.root));
  tree.breadthFirstSearch();
  
  //     9
  //  4     20
  //1  6  15  170
  
  function traverse(node) {
    const tree = { value: node.value };
    tree.left = node.left === null ? null : traverse(node.left);
    tree.right = node.right === null ? null : traverse(node.right);
    return tree;
  }
```
#
**[Back to The TOP](#section-overview)**

### <a name="code-dfs">depthFirstSearch()</a>

**JavaScript Example**:

```
class Node {
    constructor(value) {
      this.left = null;
      this.right = null;
      this.value = value;
    }
  }
  
  class BinarySearchTree {
    constructor() {
      this.root = null;
    }
    insert(value) {
      const newNode = new Node(value);
      if (this.root === null) {
        this.root = newNode;
      } else {
        let currentNode = this.root;
        while (true) {
          if (value < currentNode.value) {
            //Left
            if (!currentNode.left) {
              currentNode.left = newNode;
              return this;
            }
            currentNode = currentNode.left;
          } else {
            //Right
            if (!currentNode.right) {
              currentNode.right = newNode;
              return this;
            }
            currentNode = currentNode.right;
          }
        }
      }
    }
    lookup(value) {
      if (!this.root) {
        return false;
      }
      let currentNode = this.root;
      while (currentNode) {
        if (value < currentNode.value) {
          currentNode = currentNode.left;
        } else if (value > currentNode.value) {
          currentNode = currentNode.right;
        } else if (currentNode.value === value) {
          return currentNode;
        }
      }
      return null;
    }
    remove(value) {
      if (!this.root) {
        return false;
      }
      let currentNode = this.root;
      let parentNode = null;
      while (currentNode) {
        if (value < currentNode.value) {
          parentNode = currentNode;
          currentNode = currentNode.left;
        } else if (value > currentNode.value) {
          parentNode = currentNode;
          currentNode = currentNode.right;
        } else if (currentNode.value === value) {
          //We have a match, get to work!
  
          //Option 1: No right child:
          if (currentNode.right === null) {
            if (parentNode === null) {
              this.root = currentNode.left;
            } else {
              //if parent > current value, make current left child a child of parent
              if (currentNode.value < parentNode.value) {
                parentNode.left = currentNode.left;
  
                //if parent < current value, make left child a right child of parent
              } else if (currentNode.value > parentNode.value) {
                parentNode.right = currentNode.left;
              }
            }
  
            //Option 2: Right child which doesnt have a left child
          } else if (currentNode.right.left === null) {
            if (parentNode === null) {
              this.root = currentNode.left;
            } else {
              currentNode.right.left = currentNode.left;
  
              //if parent > current, make right child of the left the parent
              if (currentNode.value < parentNode.value) {
                parentNode.left = currentNode.right;
  
                //if parent < current, make right child a right child of the parent
              } else if (currentNode.value > parentNode.value) {
                parentNode.right = currentNode.right;
              }
            }
  
            //Option 3: Right child that has a left child
          } else {
            //find the Right child's left most child
            let leftmost = currentNode.right.left;
            let leftmostParent = currentNode.right;
            while (leftmost.left !== null) {
              leftmostParent = leftmost;
              leftmost = leftmost.left;
            }
  
            //Parent's left subtree is now leftmost's right subtree
            leftmostParent.left = leftmost.right;
            leftmost.left = currentNode.left;
            leftmost.right = currentNode.right;
  
            if (parentNode === null) {
              this.root = leftmost;
            } else {
              if (currentNode.value < parentNode.value) {
                parentNode.left = leftmost;
              } else if (currentNode.value > parentNode.value) {
                parentNode.right = leftmost;
              }
            }
          }
          return true;
        }
      }
    }
    BreadthFirstSearch() {
      let currentNode = this.root;
      let list = [];
      let queue = [];
      queue.push(currentNode);
  
      while (queue.length > 0) {
        currentNode = queue.shift();
        list.push(currentNode.value);
        if (currentNode.left) {
          queue.push(currentNode.left);
        }
        if (currentNode.right) {
          queue.push(currentNode.right);
        }
      }
      return list;
    }
    BreadthFirstSearchR(queue, list) {
      if (!queue.length) {
        return list;
      }
      const currentNode = queue.shift();
      list.push(currentNode.value);
  
      if (currentNode.left) {
        queue.push(currentNode.left);
      }
      if (currentNode.right) {
        queue.push(currentNode.right);
      }
  
      return this.BreadthFirstSearchR(queue, list);
    }
    DFSInOrder() {
      return traverseInOrder(this.root, []);
    }
    DFSPostOrder() {
      return traversePostOrder(this.root, []);
    }
    DFSPreOrder() {
      return traversePreOrder(this.root, []);
    }
  }
  
  function traverseInOrder(node, list) {
    console.log(node.value);
    if (node.left) {
      traverseInOrder(node.left, list);
    }
    list.push(node.value);
    if (node.right) {
      traverseInOrder(node.right, list);
    }
    return list;
  }
  
  function traversePreOrder(node, list) {
    console.log(node.value);
    list.push(node.value);
    if (node.left) {
      traversePreOrder(node.left, list);
    }
  
    if (node.right) {
      traversePreOrder(node.right, list);
    }
    return list;
  }
  
  function traversePostOrder(node, list) {
    console.log(node.value);
    if (node.left) {
      traversePostOrder(node.left, list);
    }
  
    if (node.right) {
      traversePostOrder(node.right, list);
    }
    list.push(node.value);
    return list;
  }
  
  const tree = new BinarySearchTree();
  tree.insert(9);
  tree.insert(4);
  tree.insert(6);
  tree.insert(20);
  tree.insert(170);
  tree.insert(15);
  tree.insert(1);
  
  // console.log("BFS", tree.BreadthFirstSearch());
  // console.log("BFS", tree.BreadthFirstSearchR([tree.root], []));
  
  console.log(tree.DFSPostOrder());
  //     9
  //  4     20
  //1  6  15  170
  
  function traverse(node) {
    const tree = { value: node.value };
    tree.left = node.left === null ? null : traverse(node.left);
    tree.right = node.right === null ? null : traverse(node.right);
    return tree;
  }
```
#
**[Back to The TOP](#section-overview)**

### <a name="d-b">Dijkstra + Bellman-Ford Algorithms</a>

- **Efficiency**: Dijkstra's algorithm is generally more efficient for graphs with non-negative edge weights. Bellman-Ford is less efficient but more versatile in handling graphs with negative weights.
- **Edge Cases**: Bellman-Ford can detect negative cycles, making it robust in scenarios where this needs to be identified.
- **Complexity**: Dijkstra's algorithm has a time complexity of O(V^2) with an adjacency matrix or O((V + E) * log(V)) with an adjacency list. Bellman-Ford has a time complexity of O(VE).

In summary, if your graph has non-negative edge weights, Dijkstra's algorithm is a great choice due to its efficiency. 

If negative weights are a consideration or if you need to detect negative cycles, then Bellman-Ford is more suitable despite its higher time complexity.

**[Back to The TOP](#section-overview)**