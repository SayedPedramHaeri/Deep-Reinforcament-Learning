## Dynamic Programming: Model-Based Reinforcement Learning

### Key Approaches:
- **Policy Evaluation**
- **Policy Improvement**
- **Policy Iteration Algorithm**
- **Value Iteration Algorithm**

### Key Concepts:

  To recap briefly, we review the necessary materials for these algorithms; however, you can see more details in the mentioned references at the end of this summary. 
  
- **Basic Definitions:**

  The Return defines the sum of all obtained rewards for one episode. In RL, the goal is to find a policy to achieve the maximum return, not the current reward. If you consider the Chess game, we want to make our decisions at each step to finally win the game, not just take the horse of our opponent.
    
  The discounted return helps us control the effect of the current reward and the future rewards in our decisions. It also helps us to avoid infinite values for our returns. 
    


- **Policy Evaluation (Bellman Expectation Equation):**

  The value of each state under a given policy is the expected discounted return when starting in the considered state and moving according to the given policy. If the policy and the environment are deterministic, the state value is equal to the discounted return; however, it has an expectation (weighted mean) form for stochastic policies and/or environments. Inspired by the recursive format of the discounted return, the state value function under a given policy is defined using Bellman's backward induction, which is called the Bellman Expectation Equation.

    
  Now, the policy evaluation uses the iterative format of the above formula to compute the state values under a given policy by initializing the value function with zeros for all states and converging to the true values.
    
- **Policy Improvement (V to Q Relationship in Bellman Expectation Equation):**

  We can compute the value of each state under a given policy by using the definition of the state value function; however, we need to define the state-action value function under a given policy so that we can improve the policy to reach the optimal policy for the considered environment. The state-action value function is the expected discounted return when starting in the considered state, choosing the first action, and then moving according to the given policy. If the policy and the environment are deterministic, the state-action value is equal to the state value and discounted return; however, it has an expectation (weighted mean) form for stochastic policies and/or environments. Again, inspired by the recursive format of the discounted return, the state-action value function under a given policy is defined using Bellman backup.
    
    
- **Policy Iteration Algorithm (Policy Evaluation + Policy Improvement):**

  The policy iteration algorithm iterates on policy evaluation and policy improvement to reach the optimal policy and optimal state values. In this algorithm, we initialize our policy and then at each iteration, we evaluate the state values under the current policy and improve our policy greedily using the computed state values; thus, the new policy and the state value function are better than the previous ones. Once we do not see any improvement in our policy, we have converged to the optimal policy and state values. 
    
- **Value Iteration Algorithm (Bellman Optimality Equation):**
  
  The optimal state value function is the best value that we can have for an environment, which is obtained by the optimal policy. If we pay attention to the definitions and formulations of optimal state value function and optimal state-action value function, we can see that the optimal state value is just its best state-action value.
  ![image
  
    
  In this algorithm, we initialize the state value function with zeros for all states, iterate on the Bellman Optimality Equation to compute the state-action values and then improve the state values greedily as the best state-action values. Thus, the new state value function is better than the previous one. Once we do not see any improvement in our state value function, we have converged to the optimal state values. Then, the optimal policy is obtained using the optimal state-action value function.
    
