
# Hangman AI — HMM + Reinforcement Learning

This project implements an **intelligent Hangman solver** that combines **Hidden Markov Models (HMM)** for probabilistic word modeling with a **Deep Q-Network (DQN)**-based reinforcement learning agent.
The goal is to teach an AI to strategically guess letters and solve Hangman words efficiently.

---

## Overview

The notebook trains and evaluates an RL agent capable of playing Hangman autonomously.
It integrates statistical modeling (HMM) with reinforcement learning (DQN) to balance exploration and exploitation when guessing letters.

**Key Features:**

* Simulated Hangman environment within the notebook
* HMM-based probability estimation of word likelihood
* DQN agent trained with experience replay and target updates
* Evaluation on unseen test words
* Reward-based learning with penalties for incorrect guesses

---

## Methodology

### 1. Environment

* Observations: Encoded word state (revealed and unrevealed letters)
* Actions: Choose a letter from A–Z
* Rewards:

  * +1 for correct letter
  * −1 for incorrect letter
  * +5 for solving the word

### 2. Hidden Markov Model (HMM)

Used to estimate the probability of potential words given partial letter information.
The probabilities guide the RL agent toward more likely predictions.

### 3. Reinforcement Learning (DQN)

* Implemented using **PyTorch**
* Learns a Q-function mapping game states → expected return for each action
* Trained via **experience replay** and **target network** for stable learning
* Uses ε-greedy exploration for action selection

---

## Results

The trained model was evaluated on 2000 unseen words.
It achieved a significantly higher win rate and average reward compared to random or heuristic baselines, demonstrating effective learning of letter-guessing strategies.

---

## Usage

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/ML_Hackathon_Hangman.git
cd ML_Hackathon_Hangman
```

### 2. Open the Notebook

Open **ML_Hackathon_Hackman.ipynb** in Jupyter or Google Colab.

### 3. Run All Cells

The notebook includes:

* Model training
* Evaluation on test words
* Visualization of results

## Dependencies

Install required libraries before running:

```bash
pip install torch numpy pandas matplotlib tqdm scikit-learn
```

