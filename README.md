# cardiacBoolNet
## Cardiac Boolean Gene Network Simulation

This project simulates cardiac gene networks using Boolean and fuzzy logic to explore how disease conditions affect cardiac gene regulatory dynamics. Inspired by **Grieb et al. (2015)** and **Borriello & Daniels (2021)**, this model investigates how gene expression variability, uncertainty, and disease conditions (like gene overexpression or loss-of-function mutations) impact network stability and attractors.

## Table of Contents

1. [Background](#background)
2. [Simulation Details](#simulation-details)
6. [Analysis and Results](#analysis-and-results)
7. [References](#references)

---

## Background

### Motivation

Understanding the dynamics of gene networks is crucial for revealing how diseases alter normal biological processes. Boolean networks are useful for studying these dynamics because they simplify complex gene interactions, making it possible to identify stable states (attractors) and understand how network stability changes under diseased conditions.

This project implements a fuzzy Boolean network to:
- Simulate normal and diseased states of cardiac gene regulatory networks.
- Identify attractors and analyze network stability.
- Compare the number and nature of fixed points and cycles between healthy and diseased networks.

### Key Papers
1. **Grieb et al. (2015)**: This paper modeled cardiac gene variability using Boolean networks, introducing uncertainty to capture gene expression’s continuous nature.
2. **Borriello & Daniels (2021)**: This study investigated control in Boolean networks, showing how biological systems can often be controlled by influencing a small set of genes.

---
## Simulation Details
Genes in the Network
This simulation models three genes central to cardiac development:

- Isl1: Plays a critical role in heart development.
- Nkx2.5: Involved in cardiac cell differentiation.
- Tbx5: A transcription factor crucial for the formation of the heart.

### Network Dynamics
The Boolean network uses fuzzy logic with fuzzy AND, OR, and NOT operators:

- AND is implemented as multiplication (A * B).
- OR as a sum minus product (A + B - (A * B)).
- NOT as the complement (1 - A).

To introduce uncertainty, slight random noise is added to each gene’s propensity (0 to 1), capturing variability in gene expression.

Attractor Analysis
- **Fixed Points:** Stable states where gene expression does not change.-

- **Cycles:** States that repeat in a sequence with a defined period.

**- Basin of Attraction: **The set of initial states that lead to the same attractor, representing the robustness of that attractor. The program identifies fixed points and cycles, allowing comparison between healthy and diseased networks.

---
## Analysis and Results
Outputs
The script prints the following information:

**- Attractors:** List of unique fixed points and cycles for both healthy and diseased networks.

**- Basin Size:** Number of initial states that lead to each attractor.

**- State Transition Graphs:** Visualizations that show how the network progresses towards attractors, illustrating the stability of healthy and diseased states.

Example Output

An example output might include:

```
Healthy Network Attractors:
Fixed Points: 2
Cycles and their Periods: [(cycle_1, 3), (cycle_2, 2)]

Diseased Network Attractors:
Fixed Points: 5
Cycles and their Periods: [(cycle_1, 2)]
```

The output helps reveal:

**- Disease Impact on Stability:** Diseased networks may have more fixed points due to simplified network dynamics.

**- Robustness Comparison:** Larger basin sizes in diseased networks can indicate increased stability in pathological states.

### Interpretation
The state transition graphs reveal key insights:

Healthy networks may exhibit fewer fixed points and more cycles, indicating greater flexibility and adaptability.


Diseased networks, with more fixed points, suggest restricted gene expression flexibility, often “locking” into maladaptive states.


### Visualizations
Two key visualizations are produced:

**- State Transition Graph:** A directed graph where each node represents a unique gene state, and edges indicate transitions.

**- Basin of Attraction Sizes:** Histograms or bar charts showing the basin sizes of each attractor, comparing network robustness between healthy and diseased states.

## References
[1] Grieb M, et al. (2015). Predicting Variabilities in Cardiac Gene Expression with a Boolean Network Incorporating Uncertainty. PLoS ONE, 10(7): e0131832.

[2] Borriello E, Daniels BC. (2021). The basis of easy controllability in Boolean networks. Nature Communications, 12:5227.


