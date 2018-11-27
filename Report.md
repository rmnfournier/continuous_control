# Project 2: Continuous Control 
## Introduction
This project was carried out as part as Udacity's Deep Reinforcement Learning nanodegree program. It was required to implement a policy-based learning algorithm to solve a continuous control task. Details regarding the environment are available in the Readme.md file, present in the repository. 

Author: Romain Fournier

Date: 27.11.2018

## Big Picture
 The task was solved by implementing a deep deterministic policy gradient algorithm (ddpg). The idea is the following. We train a Neural Network, called "actor," to find the best action possible in a given state (that's where the "deterministic policy" words come from). During the same time, we also train another network, called critic, to guess the action-value function. These two networks interact during the learning by the following way. (SARS)-sequences are placed in a replayed buffer, and the actor is used to guess the best possible action that can be performed in the landing state. The critic uses this information to update its action-value function by the self consistent equation : $Q(s_i,a)=R+\gamma*Q(s_{i+1},a_{actor})$. Then, the critic tells if the actor has taken the best action possible by comparing the reward plus the expecting return from the next state with the expected reward of the initial step. A soft update between a local and a target version of each neural network helps the model converge. I also renormalized the rewards, such that for each learning the batch has zero mean and unitary variance. 
 
   Click [here](https://arxiv.org/abs/1509.02971) to read the full description of the algorithm. 

## Neural Network Architecture
### Critic
 1. Normalize the minibatch of states
 2. ReLU applied on a linear layer (256 units)
 3. Concatenation: add the action at the bottom of the previous output
 4. ReLU applied on a linear layer (128 units)
 5. Linear layer (output dim=1)
 
### Actor
 1. Normalize the minibatch of states
 2. ReLU applied on a linear layer (256 units)
 3. ReLU applied on a linear layer (128 units)
 4. Hyperbolic tangent applied on a linear layer (output dim=4)

## Parameters 
1. Learning Rates (actor and critic): 0.001
2. Replay Buffer size: 10000
3. Batch size: 256
4. Gamma : 0.95
5. Epsilon decay: 0.9999 (used to reduce the impact of the noise during the training)

## Results
The agent managed to solve the task, i.e., reaching an average score of 30 over the last 100 episodes, in 108 episodes. 

![Training](https://github.com/rmnfournier/continuous_control/blob/master/training.png)

A movie of the trained agent is available in the repository.

## Ideas for future works
 Improving the model can be done in many ways : 
 
 1. Add the noise to the network itself, as mentioned in [this paper](https://arxiv.org/abs/1706.01905)
 2. Play with the hyperparameters
 3. Implement a prioritized replayed-buffer 
 4. Compare this approach with A2C 
