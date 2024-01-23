<h1 align="center">Data Structures: Stacks + Queues</h1>

### Section overview
* **[Trees Introduction](#trees-introduction)**
* **[Binary Trees](#binary-trees)**
* **[Binary Search Trees](#binary-search-trees)**
* **[Balanced VS Unbalanced BST](#balanced-vs-unbalanced-bst)**
* **[BST Pros and Cons](#bst-pros-and-cons)**
* **[Exercise: Binary Search Tree](#e-bst)**
* **[AVL Trees + Red Black Trees](#avl-black)**
* **[Binary Heaps](#binary-heaps)**


### Trees Introduction

Trees are a non-linear data structure that represents hierarchical data. They consist of nodes connected by edges. 

Each node can have zero or more child nodes, and each child node has exactly one parent node, except for the root node, which has no parent.

**Here are some of the key characteristics of trees**:

- **Hierarchical structure**: Trees organize data in a hierarchical manner, with each node representing a level in the hierarchy.

- **Directed edges**: The edges that connect nodes in a tree are directed, meaning that they point from a parent node to its child nodes. This ensures that there is a single path between any two nodes in the tree.

- **No cycles**: Trees do not contain any cycles or loops. This means that there is no path from a node back to itself or to any of its ancestors.

Trees are a versatile and powerful data structure that can be used for a variety of tasks, including:

- **Searching**: Trees can be efficiently searched to find a particular node or value.

- **Insertion**: New nodes can be easily inserted into trees without disrupting the existing structure.

- **Deletion**: Nodes can be deleted from trees efficiently, and the resulting tree remains well-structured.

- **Traversal**: Trees can be traversed in different ways, such as in-order, pre-order, and post-order, to visit each node once and only once.

![Trees](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/20.JPG)
#
**[Back to The TOP](#section-overview)**

### Binary Trees

A binary tree is a hierarchical data structure in which each node has at most two children, referred to as the left child and the right child. It is a type of tree data structure, where each node can have 0, 1, or 2 child nodes.

![Binary Trees](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/21.JPG)

#
**[Back to The TOP](#section-overview)**

### Binary Search Trees

A binary search tree (BST) is a tree-based data structure that efficiently stores and retrieves elements based on their keys. 

It is a sorted tree, meaning that the keys of each node are ordered in a specific way. This property allows for efficient searching, inserting, and deleting operations.

**Key Properties of Binary Search Trees**:

- **Ordered Structure**: Every node's key is greater than all keys in its left subtree and smaller than all keys in its right subtree.

- **Recursive Structure**: This property applies recursively to the left and right subtrees of each node, ensuring the overall order of the tree.

#
**[Back to The TOP](#section-overview)**

### Balanced VS Unbalanced BST

**Balanced BSTs**:
- A balanced BST maintains a well-structured tree shape, ensuring that the height of the tree is ``O(log n)``, where n is the number of elements. 
- This property guarantees efficient search, insertion, and deletion operations with an average time complexity of ``O(log n)``.

**Unbalanced BSTs**:
- An unbalanced BST can grow disproportionately, resulting in a skewed tree structure. 
- This can lead to poor performance, especially for search operations. 

![Balanced vs unbalanced](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/22.JPG)

#
**[Back to The TOP](#section-overview)**

### BST Pros and Cons

![BST Pros and Cons](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/23.JPG)

#
**[Back to The TOP](#section-overview)**

### <a name="e-bst"> Exercise: Binary Search Tree </a>

**JavaScript Class example**

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
    // INSERT data in to tree
    insert(value) {
      const newNode = new Node(value);
  
      if (this.root === null) {
        this.root = newNode;
      } else {
        let currentNode = this.root;
        while (true) {
          if (currentNode.value > value) {
            // Left
            if (!currentNode.left) {
              currentNode.left = newNode;
              return this;
            }
            currentNode = currentNode.left;
          } else {
            // Right
            if (!currentNode.right) {
              currentNode.right = newNode;
              return this;
            }
            currentNode = currentNode.right;
          }
        }
      }
    }

    // lookup or a search function
    lookup(value) {
      if (!this.root) {
        return false;
      }
      let currentNode = this.root;
  
      while (currentNode) {
        if (currentNode.value > value) {
          // Left
          currentNode = currentNode.left;
        } else if (currentNode.value < value) {
          // Right
          currentNode = currentNode.right;
        } else if (currentNode.value === value) {
          return currentNode;
        }
      }
      return false;
    }
  
  // REMOVE data from the tree - advance stuff
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
  console.log(tree.lookup(20));
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
[Core Link](https://github.com/aneagoie/ztm-master-the-coding-interview-ds-algo/blob/main/06_trees/binaryTreeImplementation.js)
#
**[Back to The TOP](#section-overview)**

### <a name="avl-black">AVL Trees + Red Black Trees</a>

In conclusion, ``AVL trees`` and ``Red-`Black` trees are invaluable in scenarios where maintaining a balanced binary search tree is essential for efficient data retrieval and modification. 

The choice between them often depends on specific use cases and the trade-offs between stricter balance (AVL) and slightly relaxed balance (Red-Black) in terms of performance and memory overhead.

### Binary Heaps


![Binary Heaps]()

#
**[Back to The TOP](#section-overview)**