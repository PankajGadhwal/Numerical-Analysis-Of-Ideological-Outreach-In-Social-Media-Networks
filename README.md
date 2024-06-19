# Numerical Analysis of Ideological Outreach in Social Media Networks

## Project Overview
This project aims to develop a numerical simulation model to analyze the process of ideological outreach within social media networks. By employing numerical methods, the study seeks to uncover the mechanisms and patterns through which various ideologies spread across digital platforms. This enables the formulation of informed strategies to understand and engage with these dissemination processes effectively.

## Table of Contents
- [Introduction](#introduction)
- [Network Model](#network-model)
- [Assumptions](#assumptions)
- [Governing Equations and Parameters](#governing-equations-and-parameters)
- [Numerical Simulation Algorithm](#numerical-simulation-algorithm)
- [Analysis](#analysis)
  - [Small Network](#small-network)
  - [Community Type Network](#community-type-network)
  - [Twitter-like Network](#twitter-like-network)
  - [Election Campaigning Analysis](#election-campaigning-analysis)
- [Results and Discussion](#results-and-discussion)
- [References](#references)

## Introduction
Understanding the dynamics of ideological outreach on social media networks is crucial for comprehending the influence of these platforms on society and politics. The aim of this project is to develop a numerical simulation model that analyzes the process of ideological outreach within social media networks.

## Network Model
A synthetic social media network is created using the NetworkX library in Python, where individuals are represented as nodes and connections as edges. The following steps are taken to generate the graph:
1. Create a graph with a fixed number of nodes.
2. Assign a random number of connections to each node based on a Gaussian distribution.
3. Connect each node to N other nodes randomly selected.
4. Store the graph as an adjacency list.
5. Assign attributes to each node, including content engagement, social interaction, receptiveness, and network position.

## Assumptions
1. A network of 1000 people is analyzed to keep the algorithm’s runtime manageable.
2. The distribution of properties, like activity and number of connections, follows a Gaussian distribution.

## Governing Equations and Parameters
### Ideology (\(i\))
Represents the current level of acceptance of an idea by a person. The growth rate is logarithmic.
### Receptiveness (\(R\))
Refers to an individual's openness to new ideologies.
### Activity (\(A\))
Measures the level of engagement within the social media network.
### Persuasiveness (\(P\))
The ability to influence others regarding specific ideologies.
### Suggestibility (\(S\))
The degree to which an individual is prone to adopting new ideologies.
### Exponential Factor (\(E\))
Represents the size of the network.

### Equations
#### Persuasion Power
\[ P_a \propto i_a A_a \]
\[ P_a = k_1 i_a A_a + c_1 \]

#### Suggestibility
\[ S_b = \frac{E}{(P_a^{-1/E-1})(E^{-S_b})} \]

## Numerical Simulation Algorithm
1. Initialize the network and assign attributes to each node.
2. Calculate persuasion power and suggestibility for each individual.
3. Simulate the propagation of ideologies using Euler's method for 100 days.
4. Update ideological values daily based on interactions between connected nodes.

## Analysis
### Small Network
Initial conditions: Ideology distribution follows a truncated Gaussian distribution.

#### Graphs
![Small Network - Initial Situation](images/small_network_initial.png)
![Small Network - After 100 Days](images/small_network_100_days.png)

### Community Type Network
#### Graphs
![Community Network - Initial Situation](images/community_network_initial.png)
![Community Network - After 100 Days](images/community_network_100_days.png)

### Twitter-like Network
#### Graphs
![Twitter-like Network - Initial Situation](images/twitter_network_initial.png)
![Twitter-like Network - After 100 Days](images/twitter_network_100_days.png)

### Election Campaigning Analysis
Aim: Analyze the factors influencing people's choices in an election.

#### Initial Conditions
- Ideology: Truncated Gaussian distribution with \( \mu = 0 \) and \( \sigma = 0.2 \).

#### Base Condition
- Party A: 33.3%
- Party B: 14.4%

![Election Base Condition](images/election_base_condition.png)

#### High Connections
- Party A given 20 people with 200 connections each.
- Party A: 39.8%
- Party B: 16.2%

![High Connections](images/election_high_connections.png)

#### High Connections vs. High Count
- Party A given 4 people with 400 connections.
- Party B given 20 people with 50 connections.
- Party A: 39.2%
- Party B: 7%

![High Connections vs. High Count](images/election_high_connections_vs_count.png)

## Results and Discussion
- Influencers significantly impact ideological propagation in small and community-type networks.
- In Twitter-like networks, the spread is rapid due to high connectivity.
- In election scenarios, highly connected individuals are more influential than a larger number of less connected individuals.

## References
1. ['Truncated Normal Distribution', Wikipedia](https://en.wikipedia.org/wiki/Truncated_normal_distribution)
2. ['Inside Twitter: An In-Depth Look Inside the Twitter World', Sysomos](https://en.wikipedia.org/wiki/Truncated_normal_distribution)
