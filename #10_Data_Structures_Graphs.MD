<h1 align="center">Data Structures: Graphs</h1>

### Section overview
* **[Graphs Introduction](#graphs-introduction)**
* **[Types Of Graphs](#types-of-graphs)**
* **[Graph Data](#graph-data)**
* **[Exercise: Graph Implementation](#e-graph)**
* **[Graphs Review](#graphs-review)**

### Graphs Review

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

### Graph Data
```
//Edge List
const graph = [[0,2],[2,3],[2,1],[1,3]];
```
```
//Adjacent List
const graph = [[2], [2,3], [0,1,3], [1,2]];
```
```
//Adjacent Matrix
const graph = {
    0: [0,0,1,0],
    1: [0,0,1,1],
    2: [1,1,0,1],
    3: [0,1,1,0]
}
```
![Graph Data](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/31.JPG)

#
**[Back to The TOP](#section-overview)**

### <a name="e-graph">Exercise: Graph Implementation</a>

**JavaScrip Class example**:

```
class Graph {
    constructor() {
      this.numberOfNodes = 0;
      this.adjacentList = {};
    }
    addVertex(node) {
      this.adjacentList[node] = [];
      this.numberOfNodes++;
    }
  
    addEdge(node1, node2) {
      //undirected Graph
      if (!this.adjacentList[node1].includes(node2)) {
        this.adjacentList[node1].push(node2);
      }
      if (!this.adjacentList[node2].includes(node1)) {
        this.adjacentList[node2].push(node1);
      }
    }
    showConnections() {
      const allNodes = Object.keys(this.adjacentList);
      for (let node of allNodes) {
        let nodeConnections = this.adjacentList[node];
        let connections = "";
        let vertex;
        for (vertex of nodeConnections) {
          connections += vertex + " ";
        }
        console.log(node + "-->" + connections);
      }
    }
  }
  
  const myGraph = new Graph();
  myGraph.addVertex("0");
  myGraph.addVertex("1");
  myGraph.addVertex("2");
  myGraph.addVertex("3");
  myGraph.addVertex("4");
  myGraph.addVertex("5");
  myGraph.addVertex("6");
  myGraph.addEdge("3", "1");
  myGraph.addEdge("3", "4");
  myGraph.addEdge("4", "2");
  myGraph.addEdge("4", "5");
  myGraph.addEdge("1", "2");
  myGraph.addEdge("1", "0");
  myGraph.addEdge("0", "2");
  myGraph.addEdge("6", "5");
  
  myGraph.showConnections();
  //Answer:
  // 0-->1 2
  // 1-->3 2 0
  // 2-->4 1 0
  // 3-->1 4
  // 4-->3 2 5
  // 5-->4 6
  // 6-->5
```

[Core Link](https://github.com/aneagoie/ztm-master-the-coding-interview-ds-algo/blob/main/07_graphs/graphImplementation.js)

#
**[Back to The TOP](#section-overview)**

### Graphs Review

![Graphs Review]()

**[Back to The TOP](#section-overview)**