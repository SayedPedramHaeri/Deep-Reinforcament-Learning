## FrozenLake Environment:
The FrozenLake-v1 environment is a classic grid-world task provided by OpenAI Gym. It models a slippery ice field where an agent must navigate from a start tile to a goal tile without falling into any holes. We have discrete action space and discrete state space.

- **Grid Layout**: 
  
  By default, there are two built-in map sizes:
  - 4×4 (the original toy example)
  - 8×8 (a larger version) 
  
  Each cell in the grid can be one of:
  - S = Start (where the agent begins)
  - F = Frozen (a safe tile)
  - H = Hole (if the agent steps here, the episode ends with zero reward)
  - G = Goal (if the agent reaches this tile, the episode ends with reward 1)
  
  <br>
  
- **Objective**:
  - Navigate from S to G by choosing “left, down, right, or up” at each step.
  - Avoid stepping on any hole (H).
  - If is_slippery=False, transitions become deterministic (no slipping).
  - If is_slippery=True, each move is stochastic: the agent may slip to a sideways tile instead of moving as intended.
  
  <br>
  
- **Reward Signal**:
  - 0 for every step that does not land on the goal.
  - 1 if the agent reaches the goal tile G.
  - Episode terminates immediately upon reaching either a hole (H) or the goal (G).
