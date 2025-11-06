#DecisionMaking #AI #Models #MDP

A **Markov Decision Process (MDP)** is a mathematical framework for modeling decision-making in situations where outcomes are partly random and partly under the control of a decision-maker. It is based on probabilities, actions, and rewards.

## Example: Navigating a Maze
* **States (S)**: The set of possible discrete positions in the maze (e.g., S = 1, 2, ..., 18).
* **Actions (A)**: The possible moves the agent can take (e.g., A = {North, East, South, West}).
* **Rewards (R)**: A numeric value given to the agent for entering a state. In the maze, reaching the goal gives a reward of +1, while all other moves give a small punishment (e.g., R = -0.1) to encourage finding the shortest path.

* **Transition Probability $T(s' | s, a)$**: This is the probability of ending up in state `s'` after taking action `a` from state `s`.
    * This models uncertainty. For example, trying to move North (`a=N`) might only have an 80% chance of success, with a 10% chance of slipping West and a 10% chance of slipping East.
    * This probability *only* depends on the previous state, which is known as the **Markov condition**.

## MDP Framework
An MDP is defined by 5 quantities:
1.  **S**: A set of states.
2.  **A**: A set of actions.
3.  **$T(s' | s, a)$**: The transition probability.
4.  **$R(r | s)$**: The probability of receiving reward `r` when getting to state `s`. This is the feedback from the environment.
5.  **$\gamma$ (gamma)**: The discount factor, which determines how much the agent values future rewards versus immediate rewards.