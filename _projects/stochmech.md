---
layout: page
title: Stochastic Electricity Markets
description: 
img: assets/img/renewable.webp
importance: 1
category: work
related_publications: singhal2026truthful
---

As renewable energy penetration increases, electricity markets face a critical design problem that traditional mechanisms cannot solve.

**The Core Issue:**
- Wind and solar generators introduce fundamental uncertainty into power supply
- This uncertainty triggers significant reserve capacity procurement and balancing costs to keep the grid stable
- However, conventional day-ahead markets optimize only for energy volume—they completely ignore balancing costs in their objective function
- Result: market outcomes are inefficient, with unnecessary costs for reserve activation

**The Missing Incentive:**
Researchers have proposed two-stage clearing mechanisms that do account for ancillary service costs. But there's a catch: **no one has designed a payment mechanism that incentivizes generators to honestly report their true forecast distribution.**

Why is this crucial? Because forecast distributions are private information—especially for hybrid power plants with on-site storage or flexible operations. Plant owners have access to the best forecasts, but without proper incentives, they'll strategically misreport to improve their profits, even if it hurts everyone else.

For instance: generators with higher forecast uncertainty may be excluded from day-ahead dispatch because the system must over-procure expensive reserve capacity to cover their potential shortfalls. This creates a perverse incentive—generators have strong motivation to *underreport* their true uncertainty to appear more reliable and get dispatched in the day-ahead market, even though this makes the system less robust and more expensive. The result: market operators work with falsified information, leading to inefficient resource allocation and higher balancing costs.

This problem is especially acute in grids with *high* renewable penetration. In low renewable penetration markets, renewable producers are always dispatched, creating no incentive to misreport. But at high penetration, uncertainty matters more due to rising ancillary service costs.

## Our Solution: VCG Mechanism Extended to Two Stages

We extend the **Vickrey-Clarke-Groves (VCG) mechanism**—a classical mechanism design result with exceptional properties—to the two-stage electricity market setting.

**Why VCG?**
- **Incentive Compatibility**: Truthful reporting is always the optimal strategy for every participant, regardless of what others do
- **Individually Rational**: Participants always recive a non-negative utility
- **Efficiency**: The market outcome maximizes total social welfare

**How it Works in Two Stages:**

1. **Day-Ahead Stage**: Generators report their production forecast distribution (mean, variance, flexibility), and the market clears with day-ahead dispatch including unit committment.
2. **Real-Time Stage**: Generators report their realized production, and the market clears with final dispatch including any production adjustments.

The magic is in the payment rule: it's designed so that generators are compensated not just for energy, but also for the *value of their flexibility and predictability*.

**Numerical Validation:**
We demonstrate the mechanism through experiments with heterogeneous agents. Generators vary in the degree of flexibility and uncertainty of production.

The results validate that truthful reporting is optimal for each type of generator.

**Understanding the Payment Rule:**
The resulting payment structure has interesting properties:
- The second-stage payment depends on *both* what the generator reported about their distribution in day-ahead *and* what actually materialized in real-time
- Generators with higher flexibility or lower uncertainty receive higher payments (reflecting the value they provide to grid reliability)
- The system correctly prices the trade-off between volume, flexibility, and predictability

## Conclusion: Pricing Predictability in Power Markets

Electricity is fundamentally different from other commodities. It's not just the *volume* that matters, but also the *predictability* and *controllability* of that supply due to grid physics and stability constraints.

Our two-stage truthful mechanism enables markets to properly value these dimensions. By combining two-stage clearing (which accounts for balancing costs) with incentive-compatible payments (which reward honest uncertainty reporting), we create markets that:

- Allocate resources efficiently despite renewable uncertainty
- Incentivize generators to invest in forecasting and flexibility
- Enable efficient high-renewable penetration markets

The result: electricity becomes a more sophisticated commodity where uncertainty and flexibility are priced alongside volume, creating efficient, fair, and sustainable power markets.
