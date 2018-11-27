# Continuous Control
The 2nd project of Udacity's Deep Learning Nanodegree program

## Instructions
project.ipynb file provides a clear way for downloading the environment and train/watch the agent. Tuning the agent can easily be done my chaning the parameters at the top of ddpg_agent.py. Changing the neural network structure is achieved by modifying model.py. 

## Environment 

![movie](https://github.com/rmnfournier/continuous_control/blob/master/reacher.gif)

The agent (the robotic arm) must stay in contact with the blue sphere. We trained 20 agents in parallel. The state-space has 33 features per agent, and each action is a set of 4 real number between -1 and 1. The environment is considered solved when the average scored over the agents, and the 100 last episodes are higher than 30. 

## Training Curve
Here are the results of the training. 

![training](https://github.com/rmnfournier/continuous_control/blob/master/training.png) 