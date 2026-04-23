# Karachi Smart Transport Planner

This repository contains a complete solution for the **Karachi Smart Transport Planner** assignment. The project models Karachi as a weighted transport graph and solves the problem using classical AI search and optimization techniques.

## Student Information

- **Name:** Owais Ali
- **Roll No:** CS-108/2025
- **Instructor:** Sir Mudassir Majeed
- **Subject:** Advance AI
- **Note:** This is an **individual assignment**.

## Project Overview

The assignment is divided into two main parts:

### Part A - Problem Formulation
This part explains the AI problem setup, including:
- PEAS description for the route-finding agent
- PEAS description for the network-design agent
- Environment properties
- State representation
- Goal representation
- Graph-based transport model for Karachi

### Part B - Build It, Layer by Layer
This part implements the solution in three layers:

#### Layer 1 - Uninformed Search
Implemented algorithms:
- Breadth-First Search (**BFS**)
- Depth-First Search (**DFS**)
- Uniform Cost Search (**UCS**)

Purpose:
- Compare route-finding behaviour on a weighted Karachi transport graph
- Show why UCS is the correct uninformed baseline for travel-time optimization

#### Layer 2 - Heuristic Search
Implemented algorithms:
- Greedy Best-First Search
- A* Search
- IDA*

Heuristics used:
- **h1:** Scaled straight-line distance heuristic
- **h2:** Karachi landmark-based heuristic

Purpose:
- Improve search efficiency over UCS
- Compare informed and uninformed search performance
- Show that A* with a strong admissible heuristic gives the best balance of efficiency and optimality

#### Layer 3 - Local Search / Network Design
Implemented algorithms:
- Hill Climbing
- Hill Climbing with sideways moves
- Random-Restart Hill Climbing
- Simulated Annealing

Purpose:
- Select an improved **K = 8 stop transport network**
- Maximize demand coverage and useful connectivity
- Evaluate optimization performance across multiple runs

## Repository Contents

- `Complete_Assignment_Owais_Ali.docx`  
  Complete solved assignment in Word format.

- `karachi_transport_planner_complete.py`  
  Python implementation of the core algorithms used in the assignment.

- `README.md`  
  Project description and usage guide.

## Graph Model

The Karachi transport network is represented as a **weighted undirected graph**:
- **Nodes** represent Karachi areas
- **Edges** represent road links between areas
- **Weights** represent estimated travel time in minutes

This graph is used for both route planning and transport network design.

## Key Results

### Layer 1
- BFS and DFS are useful for comparison, but they are not reliable for weighted shortest-path problems.
- UCS gives the optimal route when path cost matters.

### Layer 2
- A* with the landmark heuristic (**h2**) performs best overall.
- Greedy search may expand fewer nodes, but it is not always optimal.
- IDA* provides a memory-efficient alternative.

### Layer 3
- Random-Restart Hill Climbing and Simulated Annealing both produce strong network designs.
- The best network emphasizes major Karachi hubs and cross-city corridor connectivity.

## How to Run the Python Code

Make sure Python 3 is installed, then run:

```bash
python karachi_transport_planner_complete.py
```

## Requirements

The project mainly uses standard Python libraries. If you want to regenerate the report or charts, install:

```bash
pip install python-docx pandas matplotlib
```

## Learning Objectives Covered

This project demonstrates:
- Graph search problem formulation
- Uninformed search
- Heuristic search
- Admissibility and consistency of heuristics
- Local search and optimization
- AI-based transport planning

## Conclusion

This assignment shows how AI search techniques can be applied to urban transport planning. The final recommendation from the experiments is:
- Use **UCS** as the uninformed weighted baseline
- Use **A* with h2** for practical route finding
- Use **Random-Restart Hill Climbing** or **Simulated Annealing** for network design optimization

---

If you are uploading this project to GitHub, this README provides a clean academic overview of the solution and its structure.
