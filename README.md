# Search Algorithms and Pathfinding: Enclose Horse

[![UFRRJ](https://img.shields.io/badge/UFRRJ-Computer%20Science-blue)](https://portal.ufrrj.br/)
[![License](https://img.shields.io/badge/license-MIT-green)](#)

## 📌 About the Project
Developed as Practical Assignment 1 for the Artificial Intelligence course (2026.1) at **Universidade Federal Rural do Rio de Janeiro (UFRRJ)**. 

The main objective of this project is to model the "Enclose Horse" game environment and apply graph search algorithms (both blind and informed) to guide an agent (the knight) in finding an escape route to the borders of the grid. If the knight gets completely enclosed, the system calculates a total score based on the collectable items within the reachable area.

## 🚀 Features and Supported Mechanics
The system was built with a modular architecture, encompassing environment modeling, movement logic, and the mathematical application of the algorithms:

* **State Space Modeling:** 
  * Dynamic parsing of grid matrices from `.txt` files (`geometry.txt`, `entice.txt`, `closedEnv.txt`).
  * Coordinate mapping `(x, y)`, identifying the initial position (`C`), free spaces, and handling impassable obstacles such as walls (`+`) and ponds (`%`).
* **Reward System (Enclosed State):**
  * When escape is impossible, the algorithm scans the reachable graph to calculate a score: Golden Apples (10 pts), Cherries (3 pts), Free Space (1 pt), and Bee Swarms (-5 pts).
* **Implemented Search Algorithms:**
  * **Breadth-First Search (BFS):** Structured with queues (`deque`), it guarantees the optimal path by uniformly exploring adjacent nodes, at the cost of high memory expansion.
  * **Depth-First Search (DFS):** Structured with stacks, it prioritizes continuous deepening into branches, resulting in faster execution times but potentially returning non-optimal solutions.
  * **A* Search (A-Star):** Implemented with priority queues (`heapq`), it combines the accumulated path cost with the heuristic's projected value to find the optimal path while expanding fewer nodes than BFS.
* **Heuristics Construction:**
  * **Admissible Heuristic (Linear Distance):** Based on the Manhattan distance to the nearest border (calculating left, right, top, and bottom deltas).
  * **Portal Heuristic:** An advanced heuristic model designed to handle spatial discontinuities, calculating routes through teleportation portals and comparing them against the direct distance.
* **Data Analysis and Visualization:**
  * Automated generation of graphical dashboards using the `matplotlib` library.
  * Simultaneous visual comparison among the 3 algorithms, assessing metrics such as **Expanded Nodes**, **Execution Time (ms)**, and **Path Cost**.

## 🛠️ Tech Stack
* **Main Language:** Python 3
* **Development Environment:** Jupyter Notebook (`.ipynb`)
* **Data Structures Used:** `collections.deque` (Queues/Stacks), `heapq` (Min-Heaps / Priority Queues)
* **Graphical Analysis:** Matplotlib
