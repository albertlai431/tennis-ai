# tennis-ai
A pair of reinforcement learning agents that can play tennis 🎾

Languages: Python 3.6 and Pytorch\
Environment: [Unity ML-Agents Toolkit](https://github.com/Unity-Technologies/ml-agents)

## The Environment

 
**Before Training:** *Reward: 0.0, 0.0, 0.0, 0.1, 0.1*
![Before Training ](/assets/before-training.gif "Before-training")

**After Training:** *Reward: +2.6*
![After Training ](/assets/after-training.gif "After-training")

### Actions
Actions are in the form of a continuous vector space of size 2, corresponding to horizontal and vertical movement. 

### States
Each agent receives an environment state of 8 dimensions, position and velocity of the ball and racket. They are stacked in 3 frames for each time step, giving a total vector of size 24. 

### Rewards
Each agent is given a reward of **+0.1** whenever it hits the ball over the net, accumulated throughout the episode. When either agent lets the ball hit the ground or hits it out of bounds, it received a reward of **-0.01**. The environment is _solved_ when the average maximum reward accumulated by either agent over 100 consecutive episodes reaches **+0.5**.

## Installation (Windows 10 64-bit)
1. Install [Anaconda](https://docs.anaconda.com/anaconda/install/) if you don't have it already.
2. Open Anaconda Prompt/command line/terminal 
3. Create a new environment (named tennis-env): `conda create --name tennis-env python=3.6` 
4. Activate environment: `activate tennis-env`
5. Navigate to desired directory to download project file: `cd path/to/desired/directory`
6. Clone the repository: `git clone https://github.com/albertlai431/tennis-ai` 
7. Go to dependencies directory: `cd tennis-ai/python`
8. Install dependencies (may take a while): `pip install .`
9. Install pytorch 0.4.0 with conda: `conda install pytorch=0.4.0 -c pytorch`
10. Create kernel with environment: `python -m ipykernel install --user --name tennis-env --display-name "tennis-env"`

## How to Use
1. Launch jupyter-notebook and navigate to cloned repository directory
2. Open `train.ipynb` and run the code if you would like to train the agent 💪
3. Open `test.ipynb` and run the code if you would like to observe a fully trained agent! 😃
4. **Important:** Before running any code in either of the ipynb files, click **Kernel** on the top bar, **Change kernel > tennis-env**
5. Remember to deactivate the environment in the Anaconda Prompt/command line/terminal after you are done: `conda deactivate` 
   
## Potential Issues
- The folder `Tennis_Windows_x86_64` may not always work; if you are getting a `UnityTimeOutException`, please go to [this link](https://github.com/udacity/deep-reinforcement-learning/tree/master/p3_collab-compet#Getting-Started) and replace `Tennis_Windows_x86_64` with the correct folder for your system. You may also need to modify the `env` declaration. 
