# AUTOMATED CURRICULUM LEARNING FOR REINFORCEMENT LEARNING APPLICATIONS

 # Environments:
  ## Cartpole-v0/v1
![Cartpole](https://user-images.githubusercontent.com/56117150/165373260-3ee1b77f-51fc-4bd0-a2dd-caf79c0e0c9a.gif)
  # BipedalWalker-v3
![walker](https://user-images.githubusercontent.com/56117150/165372944-d0418a32-e2d1-4478-8059-ee1dc2a4577e.gif)
  # Taxi-v3
![Taxiv3](https://user-images.githubusercontent.com/56117150/165373399-153b2f1f-e560-4e47-b6f7-1b50cbfe8a9d.gif)
  # MountainCar-v0
![Mountaincar](https://user-images.githubusercontent.com/56117150/165373163-c3b30e77-3ecf-4e8a-b9f4-7bfd85153fb4.gif)

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

![image](https://user-images.githubusercontent.com/56117150/165371010-470d76e9-68e8-4f59-a6a4-0b1c79ad70a1.png)


1. Student network: receives a task, and is expected to interact in the environment and learn how to solve it.

2. Teacher network: proposes tasks by observing the progress signal of the student and sampling new tasks that maximise this signal.

### **STUDENT**

The student can be any classical Deep Reinforcement Learning agent, as from its point of view, it is only expected to solve tasks provided to it. It will be trained end-to-end, using the extrinsic reward function of the task being tackled.

### **TEACHER**

The teacher should be able to follow the student progress, and propose tasks in a sequence which overall should lead to the student solving complex tasks it couldn’t before. It effectively needs to explore the space of tasks effectively, as depending on the expertise of the student the same task can be valuable or useless.
    ## Algorithm steps:

    1. We’ll call the output of the teacher agent as improvement

    2. Improvement basically measures the direction that the student agent is taking

    3. Embedded in it is the measure of quality of the action taken by the student

    4. Improvement is then used to calculate the reinforcement signal for the student agent

    5. This reinforcement signal helps student agent learn what task to perform next task

    6. Taking this as the target, student agent’s learning is improved!
    
![image](https://user-images.githubusercontent.com/56117150/165368905-4bdedbe9-d13b-40d1-b1c7-d456bde3ccfc.png)

## Experimental Setup 
    - We tested our ACL algorithm with other baselines on OpenAI Gym environment – CartPole-v1​

    ​

    - Proposed ACL algorithm with other baseline policies/algorithms including:​

    1. Random Action Policy​

    2. Q-Learning​

    3. Deep Q-Network​

    ​

    - Since these are RL tasks, we compare the rewards the RL agent gets while performing/learning the task​

    ​

    - Automatic Curriculum Learning Agent Architectures:​

    Student Agent: DNN with the architecture – I/p-FC(32)-FC(32)-O/p​

    Teacher Agent: DNN with the architecture – I/p-FC(32)-FC(32)-O/p​

    Activation: ReLU (tanh led to long slow training)
    
# Baselines 

# Q-learning
A model-free reinforcement learning algorithm to learn the value of an action in a particular state. It can handle problems with stochastic transitions and rewards without requiring adaptations.

![image](https://user-images.githubusercontent.com/56117150/165370721-4e1dafb8-2725-4dca-9c17-8bc429b45ebd.png)

For any finite Markov decision process (FMDP), Q-learning finds an optimal policy in the sense of maximizing the expected value of the total reward over any and all successive steps, starting from the current state.

# Deep-Q Learning 

Uses neural networks to approximate Q-value functions. The state is given as input and Q-value of all possible. By maintaining the memory of the experiences, and an initial policy π.

![image](https://user-images.githubusercontent.com/56117150/165370794-c74ff25d-8dc2-42a5-8ce0-49a38ca94fc2.png)

DQN leverages experience replay as a stabilization mechanism. Experience replay collects a buffer of historical transition models and randomly inserts the transition values during the Q-update function because we want to replicate the Temporal Difference target operation using our neural network rather than using a Q-table

# Experimental Results: Rewards on Cartpole-v0-v1

![image](https://user-images.githubusercontent.com/56117150/165371702-2b80f6d4-d212-43ba-a33d-a0bb992661d1.png)


![image](https://user-images.githubusercontent.com/56117150/165371904-30d60689-1d8d-48cf-96d6-a8c834dab0eb.png)


![image](https://user-images.githubusercontent.com/56117150/165371739-ce9a76b3-0128-47fd-9a66-0059af71bcf9.png)

# Exerpimental Results: Drawbacks

- It is slow!

- The associated networks take long time to run for more complex environments like BipedalWalker

- Sensitive to network depth
Shallow networks take longer to train
Deeper networks slows down the computation time

- Exploration is a necessary evil (increases convergence time as per expected solution)

# Future Works:

- We have three further (Taxi-v3, Bipedal Walker-v3, MountainCar-v0) environments from Open AI working on the existing algorithms (Q-Learning, DQN)

- We'd like to explore these environments and fit them to ACL, we expect similarly successful results as we did from CartPole!

- Explore other more efficient NN architectures that can work with more complex envs.


![image](https://user-images.githubusercontent.com/56117150/165372260-da93c683-f1ad-431f-8b31-98eb7c7b46f2.png)
![image](https://user-images.githubusercontent.com/56117150/165372277-22e8efe9-800f-4ff8-8aae-9423fc59e3ba.png)
![image](https://user-images.githubusercontent.com/56117150/165372289-99c92900-7d8f-4b93-9d84-05fc415c2c3b.png)



