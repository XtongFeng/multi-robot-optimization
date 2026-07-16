# Optimization-based Multi-Robot Task Scheduling and Performance Analysis


## 1. Project Overview

This project studies multi-robot collaborative scheduling from the perspective of combinatorial optimization.

The goal is to build a mathematical model for task assignment and path planning, design optimization-based algorithms, and analyze the performance gap between practical solutions and theoretical optimal solutions.


## 2. Research Question

How can multiple robots complete multiple tasks efficiently in an environment with obstacles and collision constraints?

Specifically:

- How should tasks be assigned to robots?
- How should collision-free paths be planned?
- How far are practical algorithms from optimal solutions?


## 3. Research Motivation

Multi-robot systems are widely used in intelligent manufacturing, logistics, and autonomous systems.

However, task allocation and path planning are coupled problems. A method that is optimal for task assignment may not lead to an optimal overall scheduling result because robot interactions and conflicts are ignored.


## 4. Research Pipeline


Environment Modeling

↓

Mathematical Formulation

↓

Task Assignment

↓

Path Planning

↓

Conflict Resolution

↓

Performance Analysis


## 5. Main Methods

### Task Assignment

- Hungarian Algorithm
- Combinatorial Optimization


### Path Planning

- A* Algorithm
- Multi-Agent Path Finding


### Performance Analysis

Compare:

- Algorithm solution
- Exact optimal solution

Metrics:

- Total Path Cost
- Makespan
- Computational Time
- Optimality Gap


## 6. Future Work

1. Build simulation environment.
2. Implement baseline scheduling algorithms.
3. Analyze performance gap.
4. Develop conflict-aware optimization methods.
