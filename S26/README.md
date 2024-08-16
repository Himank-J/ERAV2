# Gridworld

## Psuedo Code

1. __init__
initializes the q-values of the system to empty dictionary self.qvalues 

2. getQValue
retrieve the q-value of a state and action if it is self.qvalues else return q-value = 0.0

3. computeValueFromQValue
value of a state, action is the max of all q-values of that state, possible actions.  
- get the q-values for each possible action if it is allowed by checking if action is in self.getLegalActions(state)
- max of above q-values is the computeValueFromQValue output. 
- if no possible actions can be taken the computeValueFromQValue = 0.0

4. computeActionFromQValues
for a given state, action is taken by deciding which action gives the max-q-value
- first find the best q-value which is simply the value of the state, action = V using computeValueFromQValue
- find all possible actions in that state found using actions in self.getLegalActions(state)
- find which of these actions gives the max-q-value using getQValue(state, action)
- if there are multiple actions which give the max-q-value, we chose an action randomly from them
- if there are no possible actions, we don't return action. 

5. getAction
- action taken at any state are determined by policy and epsilon (which adds randomness to the process)
- if random probability <  epsilon, then we chose a random action from all possible actions in that state
- Otherwise, we chose the action dictated by the policy using self.getPolicy(state)

6. update
function to update the q-values during q-learning. state, action, nextState, reward
- qvalue_new is set as = qvalue + alpha * (reward + disc * next_value - qvalue)
- where alpha is analogous to learning rate, reward is set by environment,  discount factor is discounts future rewards.

## Gridworld Output

https://github.com/user-attachments/assets/185f7d31-a63c-4214-afae-6fc6c3e784a9

## [Car Simulation](https://youtu.be/F1aTyMxRQTM) 📹

## Demo

https://github.com/user-attachments/assets/b6de4e77-c7b7-400b-bdf2-08c0c6d396e9

## Key Questions

Q1. What happens when "boundary-signal" is weak when compared to the last reward?

Answer: When the boundary-signal is weak relative to the last reward, the car tends to get stuck at the boundary. It struggles to return to the road or to reach its intended goal.

Q2. What happens when Temperature is reduced?

Answer: Car movement was fluctuating very rapidly. Temperature controls the exploration-exploitation trade-off. With lower T, reduced exploration and increased exploitation

Q3. What is the effect of reducing gamma? 

Answer: Reducing gamma can have averse results for RL. The agent might not focus on reaching the goal but be happy in staying on roads (achieving current rewards)

