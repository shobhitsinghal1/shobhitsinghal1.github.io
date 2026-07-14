---
layout: page
title: Local Electricity Markets
description: Iterative Market Mechanism for Local Electricity Markets
img: assets/img/elecmarket.png
importance: 1
category: work
related_publications: mlcce
---

## Why Local Energy Markets Matter

The energy transition requires efficient integration of distributed energy resources (DERs) and renewables into electricity markets. Local energy markets address this challenge by enabling:

- **Demand-side flexibility**: Consumers and prosumers can participate directly in market transactions
- **Congestion management**: Local coordination reduces network expansion costs
- **Local energy investment**: Stakeholders can invest in local energy infrastructure

However, designing these markets presents a fundamental challenge: how do we elicit and aggregate the complex, interdependent preferences of many participants while keeping participation burdens low?

## The Core Problem

**Research Gap: The Participation Burden vs. Efficiency Tradeoff**

Traditional market mechanisms force a difficult choice:

- **Simple mechanisms** (e.g., time-of-use prices) minimize participation burden but sacrifice efficiency
- **Complex formats** (e.g., full value function elicitation) achieve high efficiency but impose significant participation burden on prosumers

The challenge is that eliciting complete value functions is impractical for several reasons:

**High dimensionality**: A prosumer's value function maps package of products to real values. With 24 hourly energy products and 24 flexibility products, the domain is $\mathbb{R}^{48}$.

**Implicit representations**: In practice, value functions are embedded in proprietary energy management systems using rule-based control logic. There is no consensus on what parametric form the market should standardize on, making cross-prosumer comparison impossible.

**Privacy and communication**: Transmitting complete value functions raises privacy concerns and creates significant communication overhead. Moreover, computational complexity for market clearing increases substantially, limiting scalability.

**Interpretability**: Prosumers cannot easily understand or adjust their bids based on rejected offers. If a prosumer is unsatisfied with their allocated package, they must reverse-engineer the communicated value function to determine what settings to change in their energy management system—a convoluted process.

### The Solution: Package Queries

To find equilibrium prices, we do not need the entire value function, only a few carefully selected point queries. There are two types of queries:

- **Value query**: "What is your value for this specific package?"
- **Package query**: "What package do you prefer at these prices?"

We use package queries because they offer several advantages:

1. **Uniform communication**: Regardless of underlying value functions, all prosumers use the same query format
2. **Interpretability**: Prosumers can directly verify the recommended package aligns with their energy management system behavior
3. **Distributed computation**: No central authority needs to understand all value function details
4. **Privacy**: Only revealed preferences are shared, not complete value functions
5. **Scalability**: Computation is distributed, enabling large markets with heterogeneous prosumers

For more details, refer to the paper(s) below.