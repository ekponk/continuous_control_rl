# Continuous Control Project Report

## Environment

This is an example of Deep Deterministic Policy Gradient reinformcement learning in a simple game environment.
The goal is to train a double-jointed arm to stay in a "goal" location, for which a reward is given.
There are two versions of this project: a single-arm version, and a multi-arm version. This is a solution to the single-arm version.

The environment is provided as a custom Unity project from Udacity, found here in the `Reacher_Linux` folder.
The environment has 33 states. Actions are a vector of four floating point numbers, describing the torque of two joints, ranging from -1.0 to 1.0..

The basic algorithm is based on the Deep Deterministic Policy Gradient code used in the pendulum assignment.
However, I had to try multiple hyperparameters to get it to converge in a reasonable amount of time.
In general, I found this assignment to be much more sensitive to hyperparameter settings than the previous one.
I got some good ideas for this from discussions in the associated course slack channel.
In particular, my learning rates were way too low, and the number of nodes in my networks were larger than needed.

## Settings

There are two models here, an actor and a critic, that perform the evaluation and improvement steps. These are basically the same as the defaults in the provided code. The main difference was to add some code so that updates were not performed on every time step, as per the suggestions in the Benchmark Implementation.

The ddpg_agent is also mostly the same. Here I ended up increasing the size of the memory buffer to 100000 entries, and set the batch size to 64. I also tried several learning rates and ended up going with .002 for the actor and .0001 for the critic.

Here is a table of the main hyperparameter settings:

File | Parm | Setting
-----|-----|-------
ddpg_agent | BUFFER_SIZE | 10000
ddpg_agent | BATCH_SIZE | 64
ddpg_agent | TAU | 0.001
ddpg_agent | LR_ACTOR | 0.002
ddpg_agent | LR_CRITIC | 0.0001
ddpg_agent | GAMMA | 0.99
model | actor fc1 | 256
model | actor fc2 | 256
model | critic fc1 | 256
model | critic fc2 | 256
model | critic fc3 | 128
main | seed | 123

In general I found setting the hyperparameters for this assignment to be more difficult than the first assignment.

## Outcome

The run I chose to represent here solved the environment (>30) in 169 episodes.

```
Episode 10	Average Score: 0.95
Episode 20	Average Score: 0.87
Episode 30	Average Score: 1.29
Episode 40	Average Score: 1.55
Episode 50	Average Score: 1.97
Episode 60	Average Score: 2.55
Episode 70	Average Score: 3.56
Episode 80	Average Score: 4.98
Episode 90	Average Score: 7.15
Episode 100	Average Score: 9.27
Episode 110	Average Score: 12.74
Episode 120	Average Score: 16.28
Episode 130	Average Score: 19.64
Episode 140	Average Score: 22.75
Episode 150	Average Score: 25.67
Episode 160	Average Score: 28.14
Episode 169	Average Score: 30.13
Environment solved in 69 episodes!	Average Score: 30.13

```

![training](training.png)


## Future Work

I experimented with parameters and this seems to meet the requirements for the class. I'm sure it's possible to do better. 
In particular, I can see in the class forum that some people have achieved results that faster, so there is room for improvement.

A second provided assignment is basically the same but with multiple arms, which provides opportunities for sharing learning across agents. It would be interesting to try that to compare the approaches and results.
