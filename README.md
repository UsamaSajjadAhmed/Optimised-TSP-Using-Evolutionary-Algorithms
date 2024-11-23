# Evolutionary Algorithm for Solving the Travelling Salesman Problem (TSP)

This repository demonstrates the use of **evolutionary algorithms (EAs)** to solve the **Travelling Salesman Problem (TSP)**. The implementation focuses on optimizing routes by analyzing the effects of hyperparameters like population size, mutation rate, and crossover types on algorithm performance. The project is designed to parse datasets, simulate evolutionary operations, and visualize the results, providing valuable insights into combinatorial optimization.

---

### What is the Travelling Salesman Problem (TSP)?

The **Travelling Salesman Problem (TSP)** is a classic **combinatorial optimization problem** where the objective is to find the shortest possible route that visits each city exactly once and returns to the starting point. TSP is widely used in industries such as logistics, route planning, and supply chain optimization due to its practical applications. Being an **NP-hard problem**, it requires advanced techniques, like evolutionary algorithms, to approximate the best solutions efficiently.

---

## Why This Project?

The Travelling Salesman Problem (TSP) has significant real-world applications, including:
- **Logistics**: Optimizing delivery routes.
- **Route Planning**: Designing cost-effective travel paths.
- **Operations Research**: Solving complex resource allocation problems.
- **Data Science Benchmarks**: Evaluating optimization algorithms in NP-hard scenarios.

This project provides a structured framework to explore, tune, and visualize the performance of evolutionary algorithms on TSP datasets:
- **Brazil (58 cities)**: A larger, complex dataset for robust testing.
- **Burma (14 cities)**: A smaller dataset for quick experimentation.

---

## Code Overview

The implementation is divided into four key stages:

### **Part 1: Data Import and Preparation**
1. **Parsing XML Data**:
   - Import XML datasets into Jupyter notebooks.
   - Extract cities (vertices) and their respective travel costs (edges).

2. **DataFrame Creation**:
   - Convert parsed data into DataFrames for easier manipulation.
   - Optimize data handling by generating a list of DataFrames.

---

### **Part 2: Population Generation and Fitness Calculation**
1. **Random Population Generation**:
   - Generate a random population of solutions using the `random_population_generator()` function.

2. **Complete Travel Path**:
   - Ensure that all solutions form a complete loop (start and end at the same city) using `complete_loop_strings()`.

3. **Fitness Calculation**:
   - Convert city paths into tuples with `convert_travel_list_to_tuples()`.
   - Compute the total cost (fitness) of each solution using `total_cost_list()`.

4. **Population Fitness DataFrame**:
   - Compile all solutions and their fitness values into a DataFrame using `dataframe_generator()`.

---

### **Part 3: Experimentation on the Population**
1. **Tournament Selection**:
   - Select contenders using `tournament_selection()` based on user-defined tournament size.
   - Identify the best-performing solution using `tournament()`.

2. **Crossover Operations**:
   - Perform single-point crossover with `random_single_point_crossover()` or uniform crossover with `uniform_crossover()`.
   - Resolve any duplication in paths using the `check_and_fix()` function.

3. **Mutation**:
   - Apply mutation to offspring using the `mutation()` function, swapping genes (cities) to diversify solutions.
   - Replace the least-fit solutions with the mutated offspring using `update_list_with_mutants()`.

4. **Statistics Calculation**:
   - Track maximum, mean, and minimum costs across iterations using `calculate_cost_statistics()`.

---

### **Part 4: User-Defined Experimentation**
1. **Parameter Input**:
   - Users can specify:
     - Population size.
     - Tournament size.
     - Crossover type (single-point or uniform).
     - Mutation rate.
     - Number of iterations.

2. **Result Visualization**:
   - Plot and analyze max, mean, and min costs over iterations for performance evaluation.

---

## Key Features
- **Data Parsing**: Efficiently preprocess XML datasets into usable formats.
- **Evolutionary Techniques**: Includes selection, crossover, mutation, and replacement to simulate natural evolution.
- **Hyperparameter Exploration**: Test the impact of parameters like population size and mutation rate on optimization performance.
- **Data Visualization**: Visualize algorithm performance over time with dynamic plots.

---

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Evolutionary-TSP-Solver.git
   cd Evolutionary-TSP-Solver
