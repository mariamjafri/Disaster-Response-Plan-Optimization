# Disaster-Response-Plan-Optimization
Modeling and Analysis of Optimization of Disaster Relief based on factors for class: Nonlinear and Stochastic Optimization

This optimization problem is inspired by disaster relief plans, where we aim to determine the most efficient disaster response system, taking into consideration the severity of the disaster, the level of need, and the available inventory of supplies. Accordingly, this project develops the optimization model from scratch using simulation, of which the data is hypothetical.

Sets:
- Time intervals and Regions are sets modeled by:
$$
  t = {1,...N_t}
  \\
  R = {1,....N_R}
$$

Data:

- supplies needed in region k at time t is modeled by:
$$
  S_{k,t} ≥ 0
$$
- danger is modeled by
$$
  d_{k,t} ≥ 0
$$
- position of region k is modeled by
$$
  p_{k} ≥ 0
$$

Decisions:

- amount of supplies distributed to region k at time t
$$
  x_{k,t} ≥ 0
$$
- amount of supplies stored in region k at time t
$$
  I_{k,t} ≥ 0
$$

Objective:

- minimizing difference between demand for a region k at time t and the supplies consumed for that region at that time

$$
  \min ∑∑s̄_{k,t} - s_{k,t}
$$


Constraints:
- updated storage for region k at time t is dependent on storage for region k and time t-1, subtracted by the supplies being consumed at region k at time t, plus the amount of supplies distributed to region k at time t
$$
  I_{k,t} = I_{k,t-1} - S_{k,t} + x_{k,t}
$$

- amount consumed for region k at time t will always be greater than 0 and less than the demand for that region
$$
  0 ≤ S_{k,t} ≤ s̄_{k,t}
$$

- Inventory of a region k at time t must never go below 0 and amount of supplies distributed must never go below 0
$$
  I_{k,t} ≥ 0, \space x_{k,t} ≥ 0

$$

Key Features
Modeling utilizing Pyomo
Heatmap Analysis
Sensitivity Analysis using Monte Carlo Simulation

Tech Stack
Python libraries: pyomo, matplotlib, NumPy, Scikit-learn


