<p align="center">
  <img src="results/gait_capture.png" width="100%">
</p>

<h1 align="center">Learning Bipedal Walking with Reinforcement Learning</h1>

<p align="center">
  PPO • SAC • Continuous Control • Gymnasium • MuJoCo
</p>


This project explores how a Reinforcement Learning (RL) agent can learn to walk like a 2D robot by interacting with a simulated physics environment.

The agent receives information about its body position, joint angles, and movement, and learns to apply continuous motor actions in order to move forward without falling. Over many training steps, the agent gradually discovers stable walking behavior through trial and error.

To study how different RL methods behave on the same locomotion task, I trained and compared:

* **Proximal Policy Optimization (PPO)**
* **Soft Actor-Critic (SAC)**

---

## Implementation

* Training a bipedal robot agent using PPO and SAC, imported from StableBaselines3
* Recording reward growth and episode statistics using TensorBoard
* Saving trained models and testing final locomotion behavior
* Comparing convergence trends between PPO and SAC
---

## Environment Used

The project uses the **Walker2d** simulation environment from **Gymnasium**, using the physics simulator **MuJoCo**.

* **Observation Space:** body positions, velocities, joint states
* **Action Space:** continuous torque values for 6 joints

---

## Project Structure

```bash id="a5m9np"
walker2d-rl/
│
├── results/
├── ppo_experiments/
├── sac_experiments/
├── requirements.txt
└── README.md
```

---

## How to Run

Install dependencies:

```bash id="r8k4td"
pip install -r requirements.txt
```

Train PPO:

```bash id="77j59h"
python ppo_experiments/train_ppo.py
```

Train SAC:

```bash id="d5r7vo"
python sac_experiments/train_sac.py
```

Test saved agents:

```bash id="90xg9w"
python ppo_experiments/test_ppo_save.py
python sac_experiments/test_sac_save.py
```

View TensorBoard Logs:

```bash id="90xg9w"
tensorboard --logdir=logs/ppo
tensorboard --logdir=logs/sac
```

---

## Tools and Libraries Used

* Python
* Gymnasium
* MuJoCo Physics Engine
* Stable-Baselines3
* TensorBoard
* Matplotlib
* NumPy
* OpenCV

---

## Results Snapshot

### PPO vs SAC Comparison

<table>
<tr>
<td><img src="results/ppo_reward_curve.png"></td>
<td><img src="results/sac_reward_curve.png"></td>
</tr>
</table>

### Final Agent Demonstration

(Add walking demo GIF/video screenshots)

---

## Key Observations

* Both algorithms were able to learn forward locomotion over time.
* PPO showed stable and consistent reward improvement during training.
* SAC demonstrated stronger exploration and smoother policy adaptation in several runs.
* A good reward did not always correspond to more natural walking behavior.

---

## Author

Visha Sitapara
