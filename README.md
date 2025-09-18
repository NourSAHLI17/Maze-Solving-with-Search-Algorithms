# 🧩 Maze Solving with Search Algorithms

##  *Project Overview*
This project simulates a *robot navigating an unknown maze* in search of the exit while minimizing its movement cost.  
The robot can move in *8 directions*, each with different energy costs depending on terrain type (normal, wall, or water).  

We implemented and compared *four search algorithms*:  
- *BFS (Breadth-First Search)*  
- *DFS (Depth-First Search)*  
- *A\** with an *admissible Euclidean heuristic*  
- *Forward Checking* under constraint-based exploration  

The goal is to evaluate *efficiency, memory usage, and path optimality* across these methods.

---

##  *Problem Specifications*
- *Movement Costs*:  
  - Horizontal/Vertical: 1  
  - Diagonal: 1.41  
  - Into wall/border: same cost, but no movement  
  - Water terrain: 3 (H/V), 4.24 (Diagonal)  

- *Objective*:  
  Find the *least costly path* to the exit, without prior knowledge of the maze structure.  

---

##  *Implemented Algorithms*

### *1. BFS – Breadth-First Search*
- Explores the maze layer by layer.  
- Guarantees the *shortest path in steps*, but not the lowest-cost path.  

### *2. DFS – Depth-First Search*
- Explores paths deeply before backtracking.  
- Fast to implement, but often produces *suboptimal paths*.  

### *3. A\ – Informed Search**
- Uses f(n) = g(n) + h(n) with *Euclidean distance* as heuristic.  
- Achieves *optimal cost solutions* while exploring fewer nodes.  

### *4. Forward Checking – Constraint Satisfaction*
- Treats each maze cell as a variable with constraints.  
- Eliminates blocked paths early, reducing unnecessary exploration.  

---

##  *Results & Comparison*

| Algorithm            | Nodes Explored | Path Cost | Optimal? | Time (s) |
|----------------------|----------------|-----------|----------|----------|
| *DFS*              | 69             | 28        | ❌ No    | 0.00227  |
| *BFS*              | 103            | 18        | ✅ Yes   | 0.00105  |
| *A\**              | 56             | 18        | ✅ Yes   | 0.00068  |
| *Forward Checking* | 103            | 18        | ❌ No    | 0.00136  |

*A\** clearly offers the best balance: *optimal path, fewer nodes, fastest runtime*.  

---

## 📈 *Key Insights*
- *DFS*: Fast, but not optimal.  
- *BFS* & *Forward Checking*: Guarantee optimality but are computationally expensive.  
- *A\**: Best compromise — *optimal path with minimal exploration*.  

---

## 🛠️ *Tech & Implementation*
- Language: *Python* (adapt if needed)  
- Input: Maze grid (walls, water, free cells)  
- Output: Path found + cost + performance metrics  
- Visualization: Paths generated per algorithm
