# Reinforcement Learning for Safe Navigation in Assistive Robotic Systems

This repository explores robot path planning and reinforcement learning methods for safe navigation in stochastic and constrained environments. The project was developed around simulated robotic navigation scenarios, where an autonomous agent must reach a target location while considering path efficiency, uncertainty, traversal cost, and risk-aware decision-making.

The goal of this project is to compare classical search algorithms, dynamic programming methods, and model-free reinforcement learning approaches for robot navigation. Although the experiments are conducted in a simulated grid-based environment, the underlying methods are relevant to assistive robotic systems, rehabilitation-oriented robotic platforms, and autonomous agents that must operate safely around obstacles or high-cost regions.

---

## Project Overview

Safe navigation is an important problem in robotics. A robot should not only find a path to the goal, but also account for uncertainty, environmental constraints, and the cost of risky actions.

This project investigates navigation from three perspectives:

1. **Classical search-based planning**
   - BFS
   - DFS
   - Dijkstra
   - A*

2. **Model-based reinforcement learning**
   - Finite Markov Decision Process formulation
   - Policy evaluation
   - Policy improvement
   - Policy iteration
   - Value iteration

3. **Model-free reinforcement learning**
   - Monte Carlo prediction
   - Temporal Difference learning
   - Q-learning
   - SARSA
   - Exploration strategy analysis

Together, these methods provide a broad comparison between deterministic planning, stochastic decision-making, and learning-based control.

---

## Key Features

- Implemented and compared **BFS, DFS, Dijkstra, and A\*** for grid-based robot path planning.
- Evaluated path quality using path cost, explored cells, traversal efficiency, and route behavior.
- Modeled robot navigation as a **Finite Markov Decision Process** under stochastic movement uncertainty.
- Implemented **policy iteration** and **value iteration** for optimal policy generation.
- Developed model-free reinforcement learning methods including **Monte Carlo**, **TD(0)**, **Q-learning**, and **SARSA**.
- Analyzed the influence of discount factor, transition probability, learning rate, exploration rate, episode number, and training iterations.
- Integrated risk-aware reward and cost structures to encourage safer navigation around high-penalty regions.
- Visualized value functions, policy maps, trajectories, and convergence behavior.

---

## Method Summary

The project begins with classical graph-search algorithms and gradually extends into reinforcement learning.

### 1. Search-Based Path Planning

The first part compares deterministic planning algorithms:

- **BFS** explores the grid layer by layer and guarantees the shortest path in unweighted environments.
- **DFS** explores deeply before backtracking, but may generate inefficient paths.
- **Dijkstra** extends BFS by considering path cost and using a priority queue.
- **A\*** combines path cost with a heuristic estimate, reducing unnecessary node expansion while maintaining near-optimal route quality.

These algorithms are evaluated under different traversal-cost settings to study how cost-aware planning changes robot behavior.

---

### 2. Finite Markov Decision Process

The navigation problem is then formulated as a Finite Markov Decision Process:

```text
MDP = <S, A, P, R, γ>
```

where:

- `S` is the finite set of grid states,
- `A` is the set of robot actions,
- `P` is the state-transition probability model,
- `R` is the reward or cost function,
- `γ` is the discount factor.

This allows the robot to reason about stochastic movement, long-term reward, and safe policy selection.

---

### 3. Dynamic Programming

The model-based part implements:

- **policy evaluation** to estimate the value function of a given policy,
- **policy improvement** to update actions based on expected returns,
- **policy iteration** to alternate evaluation and improvement,
- **value iteration** to directly compute the optimal value function and extract an optimal policy.

These methods are used to generate optimal or near-optimal policies when the transition model and reward function are known.

---

### 4. Model-Free Reinforcement Learning

The project further explores learning from sampled robot-environment interaction.

Implemented methods include:

- **Monte Carlo prediction**
  - learns from complete episodes;
  - compares first-visit and every-visit estimation;
  - analyzes on-policy and off-policy learning.

- **TD(0)**
  - updates values online after each step;
  - studies the effect of learning rate on convergence.

- **Q-learning**
  - learns an optimal greedy policy while following an exploratory behavior policy;
  - evaluates convergence under stochastic transitions.

- **SARSA**
  - learns using the actual behavior policy;
  - compares safer on-policy updates against off-policy Q-learning.

---

## Risk-Aware Navigation

A key part of the project is the use of traversal costs and reward penalties to guide the robot away from undesirable regions.

This includes:

- high-cost zones,
- obstacles,
- risky regions,
- movement penalties,
- terminal rewards,
- stochastic action outcomes.

By modifying the reward and cost structure, the robot can learn or plan safer routes rather than simply choosing the geometrically shortest path.

This idea is relevant to assistive robotics, where a robot should consider not only reaching a target but also avoiding unsafe or uncomfortable regions around users, obstacles, or sensitive environments.

---

## Results Summary

The experiments show that:

- BFS is reliable in unweighted environments but does not account for movement cost.
- DFS can be memory-efficient but often produces poor or unstable paths.
- Dijkstra provides cost-aware optimal planning but may explore many nodes.
- A\* achieves a strong balance between search efficiency and path quality.
- Policy and value iteration can generate optimal policies when the model is known.
- Monte Carlo methods are flexible but can suffer from high variance.
- TD learning converges faster by bootstrapping from current value estimates.
- Q-learning can learn near-optimal policies through exploration.
- SARSA can be more conservative and safer in risky environments because it learns from the actual behavior policy.

Overall, the project demonstrates how search algorithms and reinforcement learning methods can be used together to analyze safe robot navigation under uncertainty.

---

## Reports

For more detailed methodology, mathematical derivations, experimental results, visualizations, and parameter analysis, please refer to the project reports:

- **Report 1**: Classical path planning, Dijkstra, A\*, Finite MDPs, policy iteration, and value iteration.
- **Report 2**: Monte Carlo methods, TD learning, Q-learning, SARSA, and convergence analysis.

---

## Relevance

This project is relevant to:

- robot path planning,
- reinforcement learning,
- safe navigation,
- assistive robotics,
- rehabilitation-oriented robotic systems,
- stochastic decision-making,
- autonomous control,
- risk-aware reward design.

Although the experiments are conducted in a simplified simulated environment, the methods provide useful foundations for robotic systems that must make safe and efficient decisions in uncertain environments.

---

## Limitations

This project has several limitations:

- The environment is simplified and grid-based.
- The robot dynamics are abstracted into discrete actions.
- The reward function is manually designed.
- Real-world sensing, perception, and continuous control are not included.
- The assistive robotics connection is conceptual rather than clinically validated.

---

## Future Work

Potential extensions include:

- continuous-state navigation,
- deep reinforcement learning,
- real-time obstacle detection,
- human-aware reward design,
- safe exploration strategies,
- multi-agent navigation,
- integration with physical assistive robots,
- testing in rehabilitation-oriented robotic scenarios.

---

## Disclaimer

This repository is intended for educational and research purposes. It is not a clinically validated navigation system or safety-certified robotic controller.

The related source code was used exclusively for the UCL COMP0037: Robotic Systems course and will not be made publicly available.

---

## Keywords

`Reinforcement Learning` `Robot Path Planning` `Safe Navigation` `Assistive Robotics` `Finite MDP` `A*` `Dijkstra` `Policy Iteration` `Value Iteration` `Monte Carlo` `TD Learning` `Q-learning` `SARSA`
