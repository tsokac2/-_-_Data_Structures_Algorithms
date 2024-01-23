<h1 align="center">Data Structures: Stacks + Queues</h1>

### Section overview
* **[Trees Introduction](#trees-introduction)**
* **[Binary Trees](#binary-trees)**
* **[Binary Search Trees](#binary-search-trees)**
* **[Balanced VS Unbalanced BST](#balanced-vs-unbalanced-bst)**
* **[BST Pros and Cons](#bst-pros-and-cons)**


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

![BST Pros and Cons]()

#
**[Back to The TOP](#section-overview)**