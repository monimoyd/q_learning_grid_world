# q_learning_grid_world
In this project, QLearning Reinforcement Learning is applied on Grid World. 

Pseudocode for various methods in qlearningAgents.py module are as below

## __init__

- Initialize all the Q value for all the state, action pairs to 0.0
- Set hyper parameters alpha (i.e. learning factor), epsilon (i.e. exploration probability), gamma (i.e. discount factor)

## getQValue
- For a given state, action pair find the Q value from Q table

- If  Q value is not found, return 0.0

- Else return Q value

## computeValueFromQValue
Input: state
Output: Best Q value

Algorithm:

- Get all the legal actions for the Input state
- If no legal actions available, return 0.0
- Otherwise, Iterate over all the legal actions
- Find the maximum of Q value over all he legal action for the state.
- Return maximum Q value

## computeActionFromQValues

Input: state
Return: Best action

Algorithm:
- Get all the legal actions
- If no legal action available return None
- Else Iterate over all actions
- Find the best action corresponding to maximum Q value
- Return the best action

## getAction

Input: state
Return: Best action having maximum Q value

Algorithm:
- Read the epsilon value i.e. exploration factor
- For input state, find all the legal actions.
- Choose a random number between 0 and 1
- If random number is less than epsilon choose any one of random legal action among all the actions with equal probability
- Otherwise (i.e. with probability 1 - epsilon), choose the best action having maximum Q value among all the legal actions for the state
- Return the best action


## update

Input: state, action. next state, reward
Return : None

Algorithm
- Read epsilon i.e exploration prabability
- Read alpha i.e. learning factor
- Read gamma i.e. discount factor
- Find all the legal actions for the next state
- If no legal action available for the next state, take maximum Q for next state as 0.0
- Otherwise, Iterate over all the legal actions,
- calculate the maximum Q value for the next state

- Set New Q Value of (state, action) pair = Previous Q Value of (state, action) pair + alpha * (reward + gamma * maximum of Q value of next state - previous Q Value of (state, action) pair)
