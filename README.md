## Continuous Control Reinforcement Learning

This is an example of Deep Deterministic Policy Gradient reinformcement learning in a simple game environment.
The goal is to train a double-jointed arm to stay in a "goal" location, for which a reward is given.
There are two versions of this project: a single-arm version, and a multi-arm version. This is a solution to the single-arm version.

Some pre-trained model weights are provided. A GPU is preferred for training.

For more information, please see the introduction to the original github project [here] ( https://github.com/udacity/deep-reinforcement-learning/tree/master/p2_continuous-control ).


## Environment

This is an example of an Actor-Critic Deep Reinforcement Learning method in a simple game environment.
The goal is to get a robot arm, with continuous joints, to track a ball.

The environment is provided as a custom Unity project from Udacity, found here in the `Reacher_Linux` folder.
The original Linux environment can be downloaded [here] (https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip).
The environment has 33 states corresponding to position, rotation, velocity, and angular velocities of the arm. 
Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

The particular algorithm used here is Deep Deterministic Policy Gradient Learning.

## Manifest


File | Description
------------------|-------------------
continuous_project.ipynb | Main ipython file
Reacher_Linux | Unity code repository
dqn_agent.py | Learning agent
model.py | PyTorch network model
checkpoint_my_actor.pth | Actor weights
checkpoint_my_critic.pth | Critic weights
install.sh | Installation
requirements.txt | Necessary modules
report.md | Report on the project
training.png | Image
README.md | This file


## Installation

1. Clone the assocated repository
2. Run the install.sh file `source install.sh`
3. `jupyter-notebook continuous_project.ipynb`
4. Follow the instructions in the notebook 







