# Continuous Control
The 2nd project of Udacity's Deep Learning Nanodegree program

## Installation 
You can follow the steps provided in the notebook to download the environment and train or watch an agent.

## Environment 

![movie](https://github.com/rmnfournier/continuous_control/blob/master/reacher.gif)

The agent (the robotic arm) must stay in contact with the blue sphere. We trained 20 agents in parallel. The state-space has 33 features per agent, and each action is a set of 4 real number between -1 and 1. The environment is considered solved when the average scored over the agents, and the 100 last episodes are higher than 30. 

## Training Curve
Here are the results of the training. 

![training](https://github.com/rmnfournier/continuous_control/blob/master/training.png) 