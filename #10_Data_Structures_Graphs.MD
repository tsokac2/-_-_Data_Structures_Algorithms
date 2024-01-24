<h1 align="center">Data Structures: Graphs</h1>

### Section overview
* **[Graphs Introduction](#graphs-introduction)**
* **[Types Of Graphs](#types-of-graphs)**

### Graphs Introduction
A graph is a data structure that consists of a set of ``nodes (vertices)`` and a set of edges connecting these nodes. 

The nodes represent entities, and the edges represent relationships between these entities. 

Graphs can be either directed or undirected, depending on whether the edges have a specific direction.

![Graphs](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/26.JPG)

#
**[Back to The TOP](#section-overview)**

### Types Of Graphs

**Directed Graphs (DiGraphs)**:
- In a directed graph, edges have a direction, indicating a one-way relationship between nodes.
- It represents asymmetric relationships between entities.

**Undirected Graphs**:
- In an undirected graph, edges have no direction, indicating a two-way relationship between nodes.
- It represents symmetric relationships between entities.

![Directed](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/27.JPG)

**Weighted Graphs**:

- Weighted graphs assign a numerical weight to each edge, representing the cost or distance between nodes.
- Useful for modeling scenarios where the relationships have associated values.

**Unweighted Graphs**:

- In contrast to weighted graphs, unweighted graphs do not assign any numerical value to edges.
- Suitable for scenarios where the relationships are binary.

![Unweighted](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/28.JPG)

**Cyclic Graphs**:

- Cyclic graphs contain cycles, which are loops of edges that start and end at the same node.
- They represent situations where a sequence of relationships can lead back to the starting point.

**Acyclic Graphs**:
- Acyclic graphs do not contain cycles, making them tree-like structures.
- Particularly useful in scenarios where avoiding repetition is crucial.

![Cyclic](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/29.JPG)

**Connected Graphs**:
- A connected graph has a path between every pair of nodes.
- It ensures that there are no isolated subgraphs within the overall structure.

**Disconnected Graphs**:
- Disconnected graphs have one or more isolated subgraphs without a path to cnnect them.
- It signifies separate components within the overall structure.

**Bipartite Graphs**:
- In a bipartite graph, nodes can be divided into two sets, and all edges connect nodes from different sets.
- Often used in modeling relationships between two distinct types of entities.

**Complete Graphs**:
- A complete graph has an edge between every pair of nodes.
- Suitable for scenarios where every pair of entities is directly connected.

**Example of - Direct Acyclic Graph**

![Direct Acyclic Graph](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/30.JPG)

#
**[Back to The TOP](#section-overview)**