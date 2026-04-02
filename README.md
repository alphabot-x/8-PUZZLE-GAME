# 8-Puzzle Solver using A* Search Algorithm

An efficient Artificial Intelligence solver for the classic **8-Puzzle problem** using the **A* (A-Star) Search Algorithm** and the **Manhattan Distance** heuristic.

## 📌 Project Overview
The 8-Puzzle consists of a $3 \times 3$ grid with 8 numbered tiles and one blank space. The objective is to reach a **Sorted Goal State** from a **Scrambled Initial State** by sliding tiles one at a time into the empty slot.

This project demonstrates the power of **Informed Search** over Uninformed Search (like BFS or DFS) by using domain knowledge to drastically prune the search space.

## 🚀 The A* Algorithm
The solver evaluates each move using the function:
**f(n) = g(n) + h(n)**

* **g(n):** The actual cost (number of moves) from the start to the current state.
* **h(n):** The **Manhattan Distance**—the sum of horizontal and vertical distances of each tile from its target position.

### Why A*?
* **Optimality:** Guarantees the shortest path to the goal.
* **Efficiency:** Reduces node exploration from ~180,000 (BFS) to approximately **~1,600** (a 99% reduction).

## 📊 Performance Comparison
| Algorithm | Nodes Explored | Optimal? | Efficiency |
| :--- | :--- | :--- | :--- |
| **BFS** (Uninformed) | ~180,000 | Yes | Very Low |
| **DFS** (Uninformed) | ~500,000+ | No | Low |
| **A* (Manhattan)** | **~1,600** | **Yes** | **High** |

## 🛠️ Key Features
* **Admissible Heuristic:** Uses Manhattan Distance to ensure the shortest path is never overlooked.
* **Priority Queue Logic:** Uses a Min-Heap (`heapq`) to always expand the most promising state first.
* **Cycle Detection:** Implements a 'Closed List' to prevent redundant state processing and infinite loops.

## 💻 How to Run
1. Ensure you have **Python 3.x** installed.
2. Clone the repository and navigate to the folder.
3. Run the solver:
   ```bash
   python solver.py
