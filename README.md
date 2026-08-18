# Monte Carlo and Simulated Annealing for the Traveling Salesman Problem

Implementation and analysis of **Monte Carlo methods, the Metropolis algorithm, and Simulated Annealing** applied to the **Traveling Salesman Problem (TSP)**.

This project was developed as part of my Bachelor's thesis in Engineering Physics at Politecnico di Milano and explores the connection between **statistical mechanics, Markov Chain Monte Carlo methods, and combinatorial optimization**.

## Overview

The project starts from concepts in statistical mechanics and develops the theoretical framework underlying **Markov Chain Monte Carlo (MCMC)** methods.

The main topics include:

* statistical ensembles and equilibrium;
* importance sampling;
* Markov chains;
* ergodicity;
* detailed balance;
* acceptance probabilities;
* the Metropolis algorithm;
* Simulated Annealing.

These concepts are then applied to the **Traveling Salesman Problem**, where the objective is to find the ordering of a set of cities that minimizes the total travel distance.

The analogy with statistical mechanics is used throughout the project:

* a TSP route corresponds to a **state** of the physical system;
* the total route length corresponds to its **energy**;
* the optimization control parameter plays a role analogous to **temperature**.

## Metropolis Algorithm

A Monte Carlo optimization algorithm based on the **Metropolis acceptance rule** is implemented and tested on different TSP configurations.

Candidate routes are generated through stochastic modifications of the current route and accepted according to their variation in total distance.

The analysis investigates the influence of:

* the control parameter;
* the initial route;
* the number of cities;
* fixed versus variable starting cities;
* the number of Monte Carlo iterations.

For relatively small TSP instances, the Metropolis algorithm can successfully converge toward the global minimum.

As the number of cities increases, however, the configuration space becomes increasingly complex and the algorithm can become trapped in **local minima**.

## Simulated Annealing

To improve the optimization performance for larger problems, the Metropolis algorithm is extended to **Simulated Annealing (SA)**.

Instead of keeping the control parameter fixed, SA progressively decreases the effective temperature during the simulation. This allows the algorithm to explore the configuration space more broadly at the beginning and progressively concentrate on low-cost configurations.

Two cooling strategies are investigated:

### Geometric Cooling

The control parameter is modified according to a geometric cooling schedule.

This approach produces relatively concentrated simulation outcomes and provides stable convergence toward short routes.

### Logarithmic Cooling

A logarithmic cooling schedule is also implemented and compared with geometric cooling.

The slower cooling allows the system to explore the configuration space for longer and increases the probability of reaching particularly low-cost solutions.

The simulations show that logarithmic cooling can reach the best identified route more frequently than geometric cooling, although its results are characterized by greater statistical dispersion.

## Main Findings

The numerical experiments highlight several important aspects of stochastic optimization:

* **Metropolis optimization is effective for small TSP instances**, but becomes increasingly vulnerable to local minima as the number of cities increases.
* Allowing the starting city to vary provides additional information about the structure of low-cost routes.
* **Simulated Annealing significantly improves the optimization strategy** for larger configuration spaces.
* The **cooling schedule is a crucial parameter** in SA performance.
* Logarithmic cooling shows a higher probability of reaching the best identified solutions, while geometric cooling tends to produce less dispersed results.
* Multiple independent runs are useful for estimating the global optimum in stochastic optimization problems.

## Implementation

The simulations were developed in:

**Wolfram Mathematica / Wolfram Language**

The implementation includes:

* geographic representation of cities;
* geodesic route-distance calculation;
* random route transformations;
* Metropolis acceptance criterion;
* fixed-temperature Monte Carlo simulations;
* Simulated Annealing;
* geometric and logarithmic cooling schedules;
* repeated stochastic simulations;
* convergence and acceptance-rate analysis;
* visualization of optimized routes and simulation histories.

## Thesis

The complete theoretical derivation, numerical analysis and discussion are available in the accompanying Bachelor's thesis:

**Theoretical and Numerical Study of Complex Statistical Systems**
*Application of Monte Carlo Methods and Simulated Annealing to the Traveling Salesman Problem (TSP)*

Bachelor's Thesis in Engineering Physics
Politecnico di Milano — Academic Year 2023/2024

## Author

**Francesco Savini**
