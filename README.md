# 🎮 CartPole-v1: Reinforcement Learning & Imitation Learning

## 🧠 Project Overview

This project focuses on solving the **CartPole-v1** environment using:
- ✅ **Policy Gradient Reinforcement Learning (REINFORCE Algorithm)**
- ✅ **Imitation Learning** based on expert demonstrations

We implemented, trained, and evaluated three different neural network architectures to determine the most efficient policy for balancing a pole on a moving cart. After identifying the best-performing model, we used it to generate expert demonstrations and trained a supervised imitation model with outstanding performance.

---

## 📁 Project Structure

- `ExpertModel.ipynb` – Training the expert agent using REINFORCE
- `ImitationLearning.ipynb` – Training an imitation agent using expert demonstrations
- `Inference.ipynb` – Running inference on trained imitation model
- `report.pdf` – Full project report with analysis and results

---

## 🚀 Training the Expert Agent

We trained three different policy gradient models using the REINFORCE algorithm:

### 🧪 Architectures

| Architecture | Hidden Layers                          | Episodes to Success |
|--------------|----------------------------------------|---------------------|
| **Small**    | 2 layers × 24 neurons each             | 1052                |
| **Medium**   | 64 → 32 neurons                        | 769                 |
| **Large**    | 256 → 64 → 32 neurons                  | ✅ **359 (Best)**   |

- **Activation (hidden):** ReLU
- **Activation (output):** Softmax
- **Optimizer:** Adam
- **Success Criteria:** Avg reward ≥ 480 over 10 episodes

---

## 🧠 Imitation Learning

After training the expert agent, we collected **25,000 (state, action)** pairs and trained a classifier to imitate the policy using supervised learning.

- ✅ **Accuracy:** ~98% on test set
- ✅ **Reward:** Avg reward = **500** (perfect!)

---

## 📊 Dataset Size Evaluation

We trained the imitation model on different dataset sizes:

| Dataset Size | Result Summary                  |
|--------------|----------------------------------|
| 50           | ❌ Poor performance              |
| 100          | ⚠️ Acceptable but not stable     |
| 500          | ✅ Good performance              |
| 1000         | ✅ Slight improvement, but saturated |

---

## 📎 Notebooks

| Notebook                  | Description                     |
|---------------------------|---------------------------------|
| ExpertModel.ipynb         | REINFORCE training              |
| ImitationLearning.ipynb   | Supervised training from expert |
| Inference.ipynb           | Evaluate trained model          |

---

## 👥 Authors

- **Ofek Naim** 
- **Hinoy Solomon** 

> Final project for **Advanced Topics in Deep Learning**, Colman 2024.
