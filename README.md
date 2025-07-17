# Disaster-Response-Plan-Optimization
Modeling and Analysis of Optimization of Disaster Relief based on factors for class: Nonlinear and Stochastic Optimization

This optimization problem is inspired by disaster relief plans, where we aim to determine the most efficient disaster response system, taking into consideration the severity of the disaster, the level of need, and the available inventory of supplies. Accordingly, this project develops the optimization model from scratch using simulation, of which the data is hypothetical.
### **Sets**
Time intervals and regions are represented by:

$$
t = \{1, \ldots, N_t\} 
R = \{1, \ldots, N_R\}
$$

### **Data Parameters**

Supplies needed in region \(k\) at time \(t\):
  
  $$
  S_{k,t}\ \geq 0
  $$

Danger level in region \(k\) at time \(t\):

  $$
  d_{k,t} \geq 0
  $$

Geographic position of region \(k\):

  $$
  p_k \geq 0
  $$


### **Decision Variables**

Amount of supplies **distributed** to region \(k\) at time \(t\):

  $$
  x_{k,t} \geq 0
  $$

Amount of supplies **stored** in region \(k\) at time \(t\):

  $$
  I_{k,t} \geq 0
  $$


### **Objective Function**

Minimize the difference between **demand** and **supplies consumed** for each region and time step:

  $$
  min∑∑s_{𝑘,𝑡}−𝑠_{𝑘,𝑡}
  $$


### **Constraints**

1. **Inventory Balance:**

   $$ 
   I_{k,t} = I_{k,t-1} - S_{k,t} + x_{k,t} 
   $$

2. **Supply should not exceed demand:**

   $$
   0 \leq S_{k,t} \leq \bar{s}_{k,t}
   $$

3. **Non-Negativity:**

   $$
   I_{k,t} \geq 0,\quad x_{k,t} \geq 0
   $$

---

Key Features
Modeling utilizing Pyomo
Heatmap Analysis
Sensitivity Analysis using Monte Carlo Simulation

Tech Stack
Python libraries: pyomo, matplotlib, NumPy, Scikit-learn


