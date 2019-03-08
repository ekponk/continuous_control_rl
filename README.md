## Continuous Control Reinforcement Learning

This is an example of Deep Deterministic Policy Gradient reinformcement learning in a simple game environment.
The goal is to train a double-jointed arm to stay in a "goal" location, for which a reward is given.
There are two versions of this project: a single-arm version, and a multi-arm version. This is a solution to the single-arm version.

Some pre-trained model weights are provided. A GPU is preferred for training.

For more information, please see the Introduction to the original github project [here] ( https://github.com/udacity/deep-reinforcement-learning/tree/master/p2_continuous-control ).


## Environment

This is an example of Deep Q Network reinformcement learning in a simple game environment.
The goal is to pick up as many of the yellow bananas as possible. 
Yellow bananas are rewarded positively, while Blue bananas are penalized.

The environment is provided as a custom Unity project from Udacity, found here in the `Banana_Linux` folder.
The original Linux environment can be downloaded [here] (https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip).
The environment has 37 states. Four actions are available: forward, backward, left and right.

Two improvements to the basic Q-Learning algorithm are implemented: experience replay, and fixed Q-targets.

## Manifest


File | Description
------------------|-------------------
continuous_project.ipynb | Main ipython file
Reacher_Linux | Unity code repository
dqn_agent.py | Learning agent
model.py | PyTorch network model
checkpoint.pth | Model weights
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







