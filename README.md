# Numerical Analysis Of Ideological Outreach In Social Media Networks

## Project Overview
This project analyzes the dynamics of ideological outreach on social media networks using numerical simulation models. By employing numerical methods, the study uncovers the mechanisms and patterns through which various ideologies spread across digital platforms, facilitating informed strategies for understanding and engaging with these processes.

## Table of Contents
1. [Problem Statement](#problem-statement)
2. [Objectives](#objectives)
3. [Network Model](#network-model)
4. [Assumptions](#assumptions)
5. [Attributes and Parameters](#attributes-and-parameters)
6. [Governing Equations](#governing-equations)
7. [Numerical Simulation Algorithm](#numerical-simulation-algorithm)
8. [Sensitivity Analysis](#sensitivity-analysis)
9. [Installation](#installation)
10. [Usage](#usage)
11. [Results](#results)
12. [Conclusion](#conclusion)

## Problem Statement
Understanding the dynamics of ideological outreach on social media networks is crucial for comprehending the influence of these platforms on society and politics. The aim of this project is to develop a numerical simulation model that analyses the process of ideological outreach within social media networks.

## Objectives
1. Create a synthetic social media network.
2. Formulate equations governing the spread of ideas within the network.
3. Define realistic initial conditions.
4. Implement numerical methods to simulate ideology propagation.
5. Conduct sensitivity analysis to identify critical parameters influencing the speed and extent of ideology spread.

## Network Model
A synthetic social media network is created using the NetworkX library in Python. Individuals are represented as nodes with attributes quantifying content engagement, social interaction, receptiveness, and network position.

## Assumptions
1. The network analyzed consists of 1000 people.
2. The properties of individuals, such as activity and number of connections, follow a Gaussian distribution.

## Attributes and Parameters
Each node in the network is characterized by:
1. **Ideology (i)** - Level of acceptance of the idea.
2. **Receptiveness (R)** - Willingness to accept and engage with new ideologies.
3. **Activity (A)** - Level of engagement within the network.
4. **Persuasiveness (P)** - Ability to influence others.
5. **Suggestibility (S)** - Proneness to adopting external ideologies.
6. **Exponential Factor (E)** - Represents the size of the network.
7. **Acceptance Value** - Ideological value at which an individual is considered to have accepted the idea.

## Governing Equations
### Persuasion Power (P)
\[ P_a = i_a A_a \]

### Suggestibility (S)
\[ S_b = i_b A_b R_b^2 \]

### Ideological Evolution
\[ \frac{di_b}{dt} = f(P_a) \cdot g(S_b) \]

### Functions for Persuasion and Suggestibility
\[ f(P_a) = \frac{E^{P_a} - 1}{E - 1} \]

For same alignment:
\[ g_1(S_b) = k_4 e^{-S_b} \]

For opposing alignment:
\[ g_2(S_b) = e^{k_5 S_b} \]

### Multi-Nodal Model
For same alignment:
\[ \frac{di}{dt} = \max \left( \frac{di_1}{dt}, \frac{di_2}{dt}, \ldots, \frac{di_m}{dt} \right) \]

For opposing alignment:
\[ \frac{di}{dt} = \min \left( \frac{di_1}{dt}, \frac{di_2}{dt}, \ldots, \frac{di_m}{dt} \right) \]

For mixed alignment:
\[ \frac{di}{dt} = \text{avg} \left( \frac{di_1}{dt}, \frac{di_2}{dt}, \ldots, \frac{di_m}{dt} \right) \]

## Numerical Simulation Algorithm
The propagation of ideology is simulated using the defined governing equations and initial conditions. Suitable numerical methods are employed to iterate through the network, updating each node's ideological alignment based on interactions with connected nodes.

## Sensitivity Analysis
Sensitivity analysis is conducted to identify critical parameters influencing the speed and extent of ideology spread in various scenarios:
1. Small Network
2. Community Type Network
3. Twitter-like Network
4. Election Campaigning Analysis

## Installation
To run this project, you need to have Python and the following libraries installed:
```bash
pip install numpy networkx matplotlib
