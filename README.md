# Grid World Reinforcement Learning Agent

## Overview
This code defines a reinforcement learning agent that learns to navigate a grid world. The grid world is a common framework for developing and testing reinforcement learning algorithms. The agent's goal is to move from the top-left corner of the grid to the bottom-right corner while maximizing its cumulative reward.

## Environment
- **Grid Size**: The environment is an `Ny` by `Nx` grid. The default size is 8x8.
- **State Space**: Each grid cell represents a unique state.
- **Action Space**: The agent can move in four directions: up, right, down, or left.
- **Rewards**: The agent receives a large positive reward for reaching the goal and a small negative reward for each step taken.

## Agent
- **Q-Table**: The agent uses a Q-table for storing the value of taking each action in each state.
- **Epsilon-Greedy Policy**: To balance exploration and exploitation, the agent initially explores the environment randomly. As it learns, it increasingly exploits its knowledge of the Q-values to make decisions.
- **Learning Parameters**: The agent's learning is controlled by the parameters epsilon (exploration rate), epsilon_decay (rate of exploration decrease), beta (learning rate), and gamma (discount factor).

## Training
- The agent is trained over a number of episodes, each representing a journey from the start to the goal.
- In each episode, the agent selects actions using its epsilon-greedy policy, updates its Q-table based on the observed rewards, and moves through the environment until it reaches the goal or the episode ends.
- The agent's exploration rate decreases after each episode, making it gradually shift from exploring to exploiting its growing knowledge.

## Output
- The training progress is printed every 10 episodes, showing the episode number, the current exploration rate, the number of steps taken, and the total reward received.
- After the final episode, the agent's learned policy (the best action in each state) is displayed.

## Usage
Run the script to train the agent. Modify `N_episodes` to change the number of episodes for training. Ensure `numpy` is installed for matrix operations and `random` for random number generation.

## Key Concepts
- **State Dimension**: Dimensions of the grid representing the state space.
- **Action Dimension**: Number of possible actions the agent can take.
- **Epsilon Decay**: Rate at which the agent's exploration probability decreases.
- **Learning Rate (Beta)**: The rate at which the agent incorporates new information into its Q-values.
- **Discount Factor (Gamma)**: The degree to which future rewards are taken into account in the Q-value update.

## Conclusion
This script is a basic implementation of a Q-learning agent in a grid world environment. It illustrates foundational concepts in reinforcement learning like exploration vs. exploitation, Q-value updates, and policy derivation from learned values.
