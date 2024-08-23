
# 📝 COMPSCI 2XC3 Final Project Report

## 📜 Project Overview

Welcome to the final project report for **COMPSCI 2XC3** at McMaster University. This project, conducted by Arshnoor Kaur, Garv Rastogi, and Zain Siddiqui under the guidance of Dr. Swati Mishra, focuses on implementing and analyzing various shortest path algorithms. The aim is to evaluate their performance, efficiency, and applicability in different scenarios.

## 📚 Table of Contents

1. [Introduction](#introduction)
2. [Single Source Shortest Path Algorithms](#single-source-shortest-path-algorithms)
    - [Dijkstra’s Algorithm](#dijkstras-algorithm)
    - [Bellman-Ford Algorithm](#bellman-ford-algorithm)
3. [Performance Analysis](#performance-analysis)
    - [Experiment 1: Number of Runs](#experiment-1-number-of-runs)
    - [Experiment 2: Maximum Allowed Relaxations](#experiment-2-maximum-allowed-relaxations)
    - [Experiment 3: Graph Size](#experiment-3-graph-size)
    - [Experiment 4: Graph Density](#experiment-4-graph-density)
4. [Time Complexity Analysis](#time-complexity-analysis)
5. [Accuracy Analysis](#accuracy-analysis)
6. [All-Pairs Shortest Path Algorithm](#all-pairs-shortest-path-algorithm)
7. [A* Algorithm](#a-algorithm)
    - [Issues with Dijkstra's Algorithm](#issues-with-dijkstras-algorithm)
    - [Empirical Testing Methodology](#empirical-testing-methodology)
    - [Comparison with Arbitrary Heuristic Function](#comparison-with-arbitrary-heuristic-function)
    - [Applications of A*](#applications-of-a)
8. [Adapter Pattern in A* Algorithm](#adapter-pattern-in-a-algorithm)
9. [Design Principles and Patterns](#design-principles-and-patterns)
    - [Encapsulation](#encapsulation)
    - [Inheritance](#inheritance)
    - [Polymorphism](#polymorphism)
    - [Abstraction](#abstraction)
10. [Class Hierarchy and Implementation Details](#class-hierarchy-and-implementation-details)
11. [Conclusion](#conclusion)

## 🚀 Introduction

This project explores and compares different shortest path algorithms, focusing on Dijkstra’s and Bellman-Ford algorithms, and investigates the A* algorithm as a more advanced alternative. Our goal is to implement these algorithms and analyze their performance in various scenarios to gain insights into their efficiency and practical applications. We aim to understand the trade-offs between different algorithms and determine which is best suited for specific types of problems.

## 🔍 Single Source Shortest Path Algorithms

### Dijkstra’s Algorithm

Dijkstra’s algorithm is a classic approach for finding the shortest path from a single source node to all other nodes in a graph with non-negative edge weights. The algorithm maintains a set of nodes with known shortest paths and iteratively expands this set by choosing the node with the smallest tentative distance. 

**Key Aspects:**
- **Relaxation:** Updates the shortest path estimate for a node based on the current path. This process occurs \( n-1 \) times, where \( n \) is the number of nodes.
- **Constraints:** In our project, we modified Dijkstra’s algorithm to limit the number of times each node can be relaxed to a maximum of \( k \), where \( 0 < k < N - 1 \). This constraint helps in analyzing the effect of limited relaxation on performance and accuracy.

### Bellman-Ford Algorithm

The Bellman-Ford algorithm is designed to find the shortest paths from a single source node to all other nodes, even in graphs with negative edge weights. It repeatedly relaxes all edges and can detect negative weight cycles.

**Key Aspects:**
- **Relaxation:** Similar to Dijkstra’s, but can handle negative edge weights. The algorithm performs relaxation for \( n-1 \) iterations.
- **Constraints:** In our project, we also modified Bellman-Ford to limit the number of relaxations per node to \( k \). This allows us to compare its performance under similar constraints as Dijkstra’s.

## 📊 Performance Analysis

### Experiment 1: Number of Runs

This experiment evaluates how the performance of the modified Dijkstra’s and Bellman-Ford algorithms changes with the number of runs. By varying the number of executions, we assess the algorithms' consistency and efficiency in handling multiple scenarios.

### Experiment 2: Maximum Allowed Relaxations

We analyzed the impact of varying the maximum allowed relaxations \( k \) on algorithm performance. This involves observing how different values of \( k \) affect accuracy and execution time, helping to understand the trade-offs associated with limiting node relaxations.

### Experiment 3: Graph Size

This experiment investigates how changes in graph size (i.e., the number of nodes) influence the performance of the algorithms. We measured the algorithms' scalability and efficiency as the size of the graph increases, which provides insights into their behavior in large-scale problems.

### Experiment 4: Graph Density

We examined how the density of the graph (the ratio of edges to nodes) affects the performance of the algorithms. This analysis helps in understanding how the algorithms perform in graphs with different structural properties, such as sparse versus dense graphs.

## 📈 Time Complexity Analysis

In this section, we analyze the time complexity of the implemented algorithms. We discuss how the computational requirements grow with input size and other factors, providing a theoretical understanding of the algorithms' efficiency. Time complexity analysis helps in comparing the algorithms’ performance and suitability for different problem sizes.

## 🧩 Accuracy Analysis

Accuracy analysis involves comparing the results obtained from our algorithms with known optimal solutions. By measuring how close the computed shortest paths are to the actual shortest paths, we evaluate the reliability and precision of the algorithms. This analysis helps in determining the effectiveness of each algorithm in producing correct results.

## 🌐 All-Pairs Shortest Path Algorithm

For problems requiring the shortest paths between all pairs of nodes, we designed an all-pairs shortest path algorithm. This algorithm computes the shortest paths for every possible source-destination pair in the graph.

**Key Aspects:**
- **Positive and Negative Weights:** The implementation handles both positive and negative edge weights, offering a comprehensive solution for various types of graphs.
- **Applications:** This algorithm is useful in scenarios where a complete view of shortest paths between all pairs is needed, such as in network analysis and routing problems.

## ⭐ A* Algorithm

### Issues with Dijkstra's Algorithm

A* is an enhancement over Dijkstra’s algorithm designed to address its limitations. Dijkstra’s algorithm can be inefficient in large graphs, as it explores all possible paths. A* improves efficiency by using heuristics to guide the search towards the goal more effectively.

**Key Improvements:**
- **Heuristic Function:** A* uses a heuristic to estimate the cost from the current node to the goal, reducing the number of nodes explored.
- **Efficiency:** By focusing the search on promising paths, A* can find solutions faster than Dijkstra’s in many cases.

### Empirical Testing Methodology

We developed a methodology for empirically testing and comparing Dijkstra’s and A* algorithms. This includes designing experiments to measure their performance in terms of execution time, accuracy, and efficiency. The methodology helps in understanding the practical differences between the algorithms.

### Comparison with Arbitrary Heuristic Function

We explored how A* performs compared to Dijkstra’s when using arbitrary heuristic functions. By analyzing the impact of different heuristics, we gain insights into how well A* can adapt to various problem scenarios and the effectiveness of different heuristics.

### Applications of A*

A* is particularly useful in applications where heuristics can significantly improve search efficiency. Examples include pathfinding in games, navigation systems, and robot motion planning. We examined scenarios where A* is preferred over Dijkstra’s due to its ability to leverage heuristics.

## 🔄 Adapter Pattern in A* Algorithm

We implemented the A* algorithm using the Adapter pattern to enhance its flexibility and robustness. The Adapter pattern allows us to create a flexible interface for the A* algorithm, making it easier to integrate and modify.

**Key Aspects:**
- **Adapter Pattern Overview:** Describes the pattern and its purpose in the context of the A* algorithm.
- **Implementation Steps:** Details the steps involved in applying the Adapter pattern, including creating the AStar Adapter, managing the priority queue, calculating the total cost, and implementing path retrieval and backtracking.

## 🏛️ Design Principles and Patterns

### Encapsulation

Encapsulation was applied to hide the internal implementation details of the algorithms, promoting modularity and reducing dependencies. This principle ensures that changes in the implementation do not affect other parts of the system.

### Inheritance

Inheritance was used to extend the functionality of base classes, enabling code reuse and enhancing the structure of the implementation. This principle allows for creating more specialized classes based on existing ones.

### Polymorphism

Polymorphism enables flexible method overriding and interface implementation, allowing different algorithms to be used interchangeably. This principle facilitates the integration of various algorithms into a unified system.

### Abstraction

Abstraction simplifies complex implementations by focusing on essential features and hiding unnecessary details. This principle helps in managing complexity and improving code readability.

## 📊 Class Hierarchy and Implementation Details

This section provides a detailed explanation of the class hierarchy, attributes, and methods used in the project. It includes descriptions of how different components interact, the rationale behind design choices, and the implementation details for each class.

## 🏁 Conclusion

The project successfully implemented and analyzed various shortest path algorithms, providing valuable insights into their performance and applicability. The experiments demonstrated the

 strengths and limitations of each algorithm, with A* offering significant advantages in specific scenarios. The findings help in understanding which algorithms are best suited for different types of problems and how to optimize their performance.

---

### 👥 Contributors

- **Arshnoor Kaur** - [GitHub Profile](https://github.com/kaura69)
- **Garv Rastogi** - [GitHub Profile](https://github.com/rastogig)
- **Zain Siddiqui** - [GitHub Profile](https://github.com/siddiz6)
