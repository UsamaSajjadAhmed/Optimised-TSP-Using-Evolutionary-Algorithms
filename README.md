# Evolutionary Algorithm for Solving the Travelling Salesman Problem (TSP)

This repository demonstrates the use of **evolutionary algorithms (EAs)** to solve the **Travelling Salesman Problem (TSP)**. The implementation focuses on optimizing routes by analyzing the effects of hyperparameters like population size, mutation rate, and crossover types on algorithm performance. The project is designed to parse datasets, simulate evolutionary operations, and visualize the results, providing valuable insights into combinatorial optimization.

---

## Why This Project?

The Travelling Salesman Problem (TSP) is a classic combinatorial optimization challenge with applications in:
- **Logistics**: Optimizing delivery routes.
- **Route Planning**: Designing efficient travel paths.
- **Operations Research**: Solving complex resource allocation problems.
- **Data Science Benchmarks**: Testing optimization techniques in NP-hard scenarios.

This project provides a systematic workflow to explore, tune, and visualize the performance of evolutionary algorithms in minimizing travel costs across two datasets:
- **Brazil (58 cities)**: A larger, complex dataset for robust testing.
- **Burma (14 cities)**: A smaller dataset for quick experimentation.

---

## Code Overview

The implementation is divided into four parts:

### **Part 1: Data Import and Preparation**
1. **Parsing XML Data**:
   - Import XML datasets into Jupyter notebooks.
   - Parse the data to extract vertices (cities) and their respective costs (edges).

2. **DataFrame Creation**:
   - Create a function to transform parsed data into a DataFrame for easier manipulation.
   - Generate a list of DataFrames to reduce time complexity during operations.

---

### **Part 2: Population Generation and Fitness Calculation**
1. **Random Population Generation**:
   - Generate a random solution population of user-defined size using the `random_population_generator()` function.

2. **Complete Travel Path**:
   - Ensure that paths form a complete loop (starting and ending at the same city) using the `complete_loop_strings()` function.

3. **Fitness Calculation**:
   - Convert city paths into tuples with `convert_travel_list_to_tuples()`.
   - Calculate the total cost (fitness) of each solution using the `total_cost_list()` function.

4. **Population Fitness DataFrame**:
   - Create a DataFrame of all population solutions and their fitness values with the `dataframe_generator()` function.

---

### **Part 3: Experimentation on the Population**
1. **Tournament Selection**:
   - Select contenders for reproduction using `tournament_selection()` based on user-defined size.
   - Determine the best-performing solution in the tournament using the `tournament()` function.

2. **Crossover Operations**:
   - Implement single-point crossover with `random_single_point_crossover()` or uniform crossover with `uniform_crossover()` to generate offspring.
   - Fix duplication issues in offspring paths with `check_and_fix()`.

3. **Mutation**:
   - Apply a user-defined mutation rate with the `mutation()` function, swapping pairs of cities within a solution.
   - Update the population by replacing the least-fit solutions with the mutated offspring using `update_list_with_mutants()`.

4. **Statistics Calculation**:
   - Track and store the maximum, mean, and minimum costs across iterations using `calculate_cost_statistics()`.

---

### **Part 4: User-Defined Experimentation**
1. **Parameter Input**:
   - Allow users to specify:
     - Number of contenders for the tournament.
     - Type of crossover (single-point or uniform).
     - Mutation rate and its application.
     - Number of iterations for the experiment.

2. **Result Visualization**:
   - Generate plots to visualize max, mean, and min costs across iterations for data analysis.

---

## Key Features
- **Data Transformation**: Parse and preprocess XML datasets into DataFrames for efficient analysis.
- **Evolutionary Operations**: Implement tournament selection, crossover, mutation, and population updates to simulate evolutionary optimization.
- **Hyperparameter Tuning**: Allow users to explore different configurations of population size, tournament size, crossover types, and mutation rates.
- **Performance Visualization**: Plot and analyze metrics like max, mean, and min costs to evaluate algorithm effectiveness.

---

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Evolutionary-TSP-Solver.git
   cd Evolutionary-TSP-Solver
