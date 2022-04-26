# Reinforcement-Learning
 RL paradigms explored with OpenAI

# Dependencies 
Tensorflow >=2.7
Keras >=2.7
Keras-rl2 >= 1.0.5
Numpy >=1.22.2

# Problem Description:

Gym OpenAI provides multiple test-bed environments with real world applications in robotics, with problem spaces ranging being from simple 32 Observation and 2 possible actions. To and computationally infinite action and observation space. These environments are thus incredible spaces to test the credibility of these RL paradigms. This simple project implements the three of the environments from OpenAI them being: 

1. CartPole-v0
2. Taxi-v3
3. BipedalWalker-v3

The notebooks listed here implement the baseline approachs including:
1. Random Action Approach
2. Q-Learning 
3. Deep Q-Learning

# Automatic Curriculum Learning is implemented for **CartPole-v0**

    ## Algorithm steps:

    1. We’ll call the output of the teacher agent as improvement

    2. Improvement basically measures the direction that the student agent is taking

    3. Embedded in it is the measure of quality of the action taken by the student

    4. Improvement is then used to calculate the reinforcement signal for the student agent

    5. This reinforcement signal helps student agent learn what task to perform next task

    6. Taking this as the target, student agent’s learning is improved!
![formula](https://render.githubusercontent.com/render/math?math=e^{i \pi} = -1)
