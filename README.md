# SPIN - Reinforcement Learning for Quadrotor Recovery under Rotor Failure

> **What happens when a drone loses a rotor mid-flight?** Rather than attempting to preserve conventional flight behaviour, this project explores how Reinforcement Learning can enable a quadrotor to adapt to a sudden actuator failure and maintain controlled flight.

SPIN explores Reinforcement Learning-based fault-tolerant control for quadrotors subjected to complete single-rotor failure. Conventional quadrotor control relies on the coordinated thrust of four rotors to maintain attitude and position. Losing one rotor introduces severe torque imbalance, significantly altering the dynamics of the vehicle and making conventional stabilization difficult.

Inspired by research demonstrating that quadrotors can exploit unconventional flight behaviours, including spinning manoeuvres, to remain airborne following rotor failure, this project investigates whether a Reinforcement Learning agent can learn to adapt to these altered dynamics and develop recovery strategies.

The project will focus on physics-based simulation, quadrotor dynamics, control theory, Reinforcement Learning and robust policy training in MuJoCo. Sim-to-Real techniques will also be explored to improve the potential deployability of the learned controller, with evaluation conducted entirely in simulation.

---

# 1. Project Overview

| Parameter | Details |
|---|---|
| **Project Name** | SPIN |
| **Domain** | Robotics, Reinforcement Learning, Flight Control |
| **Objective** | Quadrotor recovery under complete single-rotor failure |
| **Simulation Environment** | MuJoCo |
| **RL Algorithm** | PPO (Proximal Policy Optimization) |
| **Programming Language** | Python |
| **Framework** | PyTorch |
| **Focus Areas** | Dynamics, Control, RL, Fault Tolerance, Sim-to-Real |

## Objective

Investigate whether Reinforcement Learning can enable a quadrotor to recover or maintain controlled flight following complete failure of an individual rotor by adapting to altered flight dynamics and exploiting the remaining actuators.

## Core Idea

Rather than attempting to restore conventional four-rotor flight, the project explores alternative flight behaviours that may allow the quadrotor to remain airborne despite the loss of one actuator.

This includes investigating unconventional rotational behaviours, recovery strategies and policies capable of adapting to asymmetric thrust configurations.

---

# 2. Motivation & Problem Statement

Quadrotors are inherently dependent on the coordinated operation of their rotors to generate thrust and control rotational motion. The complete failure of one rotor disrupts this balance, introducing asymmetric forces and torques that can lead to rapid destabilization.

Under conventional control strategies, a quadrotor is designed to maintain a stable attitude while controlling its position. However, following a complete rotor failure, maintaining the same flight configuration may no longer be feasible because the available control authority has fundamentally changed.

Research has demonstrated that quadrotors can exploit unconventional flight dynamics following rotor failure, including high-speed spinning manoeuvres, to maintain flight and control certain aspects of their motion.

This presents an interesting Reinforcement Learning problem: instead of explicitly designing a recovery manoeuvre, can an agent learn a policy that adapts to the altered dynamics and discovers viable recovery behaviour through interaction with a physics-based simulation?

SPIN aims to explore this question through Reinforcement Learning-based control, focusing on recovery behaviour, robustness and adaptability under actuator failure.

### Why Reinforcement Learning?

- **Adaptability:** RL policies can learn behaviours suited to altered dynamics rather than relying entirely on predefined recovery manoeuvres.
- **Nonlinear dynamics:** Quadrotor flight involves nonlinear, coupled translational and rotational dynamics.
- **Unconventional behaviours:** Learning-based controllers may discover manoeuvres that are difficult to explicitly design using conventional control approaches.
- **Robustness:** Policies can be trained under randomized conditions to improve their ability to handle disturbances and modelling uncertainties.
- **Research potential:** Rotor failure recovery provides a challenging control problem with meaningful opportunities to investigate RL, control theory and simulation-based experimentation.

---

# 3. Project Objectives

The project aims to:

- Develop a physics-based quadrotor simulation environment in MuJoCo.
- Understand quadrotor dynamics, thrust generation and rotational motion.
- Investigate the effects of complete single-rotor failure on flight dynamics.
- Model rotor failure within the simulation environment.
- Formulate fault-tolerant recovery as a Reinforcement Learning problem.
- Implement and train a PPO-based agent for recovery following rotor failure.
- Investigate unconventional recovery behaviours, including controlled spinning.
- Experiment with reward design and different observation and action representations.
- Evaluate learned policies under varying initial conditions, disturbances and physical parameters.
- Investigate domain randomization and Sim-to-Real techniques for improving robustness and potential deployability.

---

# 4. Research & Literature

The project draws inspiration from research in fault-tolerant quadrotor control, unconventional flight manoeuvres, Reinforcement Learning-based recovery and robust control under actuator failure.

The following papers provide the foundation for understanding the problem, existing recovery approaches and potential learning-based solutions.

## 4.1 High-Speed Flight of Quadrotor Despite Loss of Single Rotor

**Paper:** High-Speed Flight of Quadrotor Despite Loss of Single Rotor

**Link:** https://doi.org/10.1109/LRA.2018.2851028

This research investigates how a quadrotor can continue flying despite losing a rotor by exploiting unconventional flight manoeuvres.

Rather than attempting to maintain conventional stabilization, the approach demonstrates how altered flight dynamics can be exploited to achieve flight under a reduced actuator configuration.

**Relevance to SPIN:**

- Understanding unconventional flight behaviour following rotor failure.
- Investigating spinning flight and altered rotational dynamics.
- Exploring the feasibility of recovery using the remaining actuators.
- Providing inspiration for RL reward design and recovery objectives.

## 4.2 A Model-free Deep Reinforcement Learning Approach To Maneuver A Quadrotor Despite Single Rotor Failure

**Paper:** A Model-free Deep Reinforcement Learning Approach To Maneuver A Quadrotor Despite Single Rotor Failure

**Link:** https://arxiv.org/abs/2109.10488

This work explores a model-free Deep Reinforcement Learning approach for manoeuvring a quadrotor despite complete single-rotor failure.

The paper provides a relevant foundation for investigating learning-based manoeuvring and adapting policies to the altered dynamics resulting from rotor failure.

**Relevance to SPIN:**

- RL-based manoeuvring under actuator failure.
- Understanding learning-based recovery strategies.
- Exploring policy learning under altered control authority.
- Informing the RL formulation and training methodology.

## 4.3 Autonomous Quadrotor Flight Despite Rotor Failure With Onboard Vision Sensors: Frames vs. Events

**Paper:** Autonomous Quadrotor Flight Despite Rotor Failure With Onboard Vision Sensors: Frames vs. Events

**Link:** https://doi.org/10.1109/LRA.2020.3048875

**PDF:** https://cs.lr.tudelft.nl/syscon/wp-content/uploads/sites/8/2023/02/Sun2021_Autonomous_Quadrotor_Flight_Despite_Rotor_Failure_With_Onboard_Vision_Sensors_Frames_vs._Events.pdf

This research investigates autonomous quadrotor flight following rotor failure using onboard vision sensors, comparing frame-based and event-based visual sensing approaches.

**Relevance to SPIN:**

- Understanding visual sensing in fault-tolerant flight.
- Exploring perception-related extensions to the project.
- Investigating the potential of vision-based observations.
- Understanding how sensing can contribute to recovery and autonomy.

## 4.4 Upset Recovery Control for Quadrotors Subjected to a Complete Rotor Failure from Large Initial Disturbances

**Paper:** Upset Recovery Control for Quadrotors Subjected to a Complete Rotor Failure from Large Initial Disturbances

**Link:** https://doi.org/10.1109/ICRA40945.2020.9197239

This research studies recovery control strategies for quadrotors subjected to complete rotor failure and significant initial disturbances.

**Relevance to SPIN:**

- Understanding recovery under severe flight disturbances.
- Investigating recovery from destabilized initial states.
- Developing evaluation scenarios involving external disturbances.
- Exploring robustness of recovery policies.

## 4.5 Reinforcement Learning-Based Fault-Tolerant Control for Quadrotor UAVs Under Actuator Fault (2024)

**Paper:** Reinforcement Learning-Based Fault-Tolerant Control for Quadrotor UAVs Under Actuator Fault

**Link:** https://doi.org/10.1109/tii.2024.3438241

This research explores learning-based fault-tolerant control strategies for quadrotor UAVs under actuator faults.

**Relevance to SPIN:**

- Understanding RL-based fault-tolerant control.
- Exploring learning-based adaptation to actuator faults.
- Investigating robustness and control under altered actuator configurations.

## 4.6 Learning-Based Passive Fault-Tolerant Control of a Quadrotor with Rotor Failure (2025)

**Paper:** Learning-Based Passive Fault-Tolerant Control of a Quadrotor with Rotor Failure

**Link:** https://arxiv.org/abs/2503.02649

This work explores learning-based passive fault-tolerant control approaches for quadrotors experiencing rotor failure.

**Relevance to SPIN:**

- Exploring passive fault-tolerant control.
- Understanding learning-based adaptation to rotor failure.
- Investigating potential alternative control strategies.

---

# 5. Week 1 — Research & Foundations

The first week focuses on building the theoretical and technical foundation required to understand the problem before beginning the primary simulation and training implementation.

The goal is to develop familiarity with quadrotor dynamics, control theory, Reinforcement Learning, rotor failure modelling and MuJoCo.

## 5.1 Quadrotor Dynamics

Understand how a quadrotor generates forces and torques through its rotor configuration and how these affect its motion.

### Topics

- Quadrotor configuration and rotor arrangement.
- Thrust generation and motor dynamics.
- Translational dynamics.
- Rotational dynamics.
- Newton-Euler equations.
- Body-frame and world-frame representations.
- Attitude representation.
- Angular velocity and angular acceleration.
- Roll, pitch and yaw.
- Rotor-generated torques.
- Coupling between translational and rotational motion.

### Learning Objectives

- Understand how rotor thrust contributes to total thrust.
- Understand how differential thrust generates rotational moments.
- Understand the relationship between angular velocity, attitude and motion.
- Analyse the effects of asymmetric thrust on quadrotor dynamics.
- Develop an intuition for the loss of stability following rotor failure.

## 5.2 Rotor Failure & Fault-Tolerant Control

Understand how a complete rotor failure changes the quadrotor's dynamics and available control authority.

### Topics

- Complete actuator failure.
- Loss of thrust from an individual rotor.
- Asymmetric thrust and torque generation.
- Effects of rotor failure on rotational motion.
- Conventional quadrotor stabilization.
- Control allocation.
- Reduced control authority.
- Fault-tolerant control.
- Unconventional flight manoeuvres.
- Spinning flight and recovery strategies.
- Reduced-attitude control concepts.

### Learning Objectives

- Understand why conventional stabilization becomes difficult following rotor failure.
- Analyse the resulting torque imbalance.
- Understand how the remaining rotors influence the vehicle's dynamics.
- Explore alternative recovery strategies.
- Develop intuition for unconventional recovery manoeuvres.

## 5.3 Reinforcement Learning Foundations

Develop the theoretical foundation required to formulate and train an RL agent.

### Topics

- Markov Decision Processes.
- State and observation spaces.
- Action spaces.
- Rewards and reward shaping.
- Policies.
- Value functions.
- Exploration and exploitation.
- Episode termination.
- Policy optimization.
- Proximal Policy Optimization.
- Actor-Critic methods.
- Training stability.
- Reward design.

### Learning Objectives

- Understand the RL interaction loop.
- Formulate the quadrotor recovery task as an MDP.
- Understand the role of observations, actions and rewards.
- Understand policy learning and optimization.
- Develop familiarity with PPO.
- Understand how reward design affects learned behaviour.

## 5.4 MuJoCo & Simulation Foundations

Develop familiarity with the physics-based simulation environment that will be used for modelling and training.

### Topics

- MuJoCo physics engine.
- Model configuration and XML.
- Rigid-body dynamics.
- Bodies, joints and actuators.
- Forces and torques.
- Simulation stepping.
- State variables.
- Physics parameters.
- Contact and collision modelling where applicable.
- Environment interaction.

### Learning Objectives

- Understand the structure of a MuJoCo model.
- Familiarize yourself with the simulation workflow.
- Understand how actuator commands influence the simulated system.
- Understand simulation state and physics stepping.
- Develop familiarity with the tools required for quadrotor simulation.

---

# 6. Mathematical & Control Foundations

The following mathematical and control concepts will be explored as they become relevant to the simulation and RL formulation.

## 6.1 Newton-Euler Dynamics

Understanding how forces and torques affect the translational and rotational motion of a rigid body.

- Newton's laws of motion.
- Force balance.
- Torque balance.
- Angular momentum.
- Rotational inertia.

## 6.2 Coordinate Frames

Understanding how the quadrotor's motion is represented in different coordinate systems.

- World frame.
- Body frame.
- Coordinate transformations.
- Rotation matrices.
- Euler angles.
- Quaternions.

## 6.3 Control Theory

Understanding the foundations of flight control and the effects of actuator failure.

- Feedback control.
- PID control.
- Attitude control.
- Control allocation.
- Stability.
- Control authority.
- System response.

## 6.4 Reinforcement Learning

Understanding the formulation and optimization of policies.

- Markov Decision Processes.
- Policy gradients.
- Actor-Critic methods.
- PPO.
- Reward functions.
- Policy evaluation.
- Exploration.

---

# 7. Proposed Methodology

The project will progressively develop the simulation environment, introduce rotor failure, formulate the RL task and investigate recovery behaviour through policy training.

## Stage 1 — Simulation Environment

Develop a physics-based quadrotor model in MuJoCo.

The environment will include:

- Quadrotor rigid-body dynamics.
- Rotor and actuator configuration.
- Thrust generation.
- Relevant state variables.
- Simulation stepping.
- Control inputs.

### Initial Goal

Establish a functioning simulation environment and verify that the quadrotor model behaves as expected under nominal flight conditions.

## Stage 2 — Rotor Failure Modelling

Introduce complete failure of one rotor during flight.

The failed rotor will no longer generate the expected thrust, resulting in an asymmetric thrust configuration and altered rotational dynamics.

### Initial Goal

- Implement rotor failure.
- Analyse the effects on flight dynamics.
- Observe the resulting instability.
- Understand the effects on angular velocity and attitude.
- Establish a repeatable failure scenario for training.

## Stage 3 — Reinforcement Learning Formulation

Formulate the recovery task as a Markov Decision Process.

### Observation Space

The initial observation space may include:

| Observation | Description |
|---|---|
| Position | Quadrotor position in the simulation frame. |
| Linear Velocity | Translational velocity. |
| Orientation | Attitude representation, such as quaternion or rotation-related features. |
| Angular Velocity | Rotational velocity around the body axes. |
| Altitude | Height above the reference plane. |
| Additional State Variables | Relevant information required for recovery and policy learning. |

The final observation representation will depend on experimentation and the requirements of the recovery task.

### Action Space

The action space will consist of motor thrust commands.

The failed rotor will be appropriately disabled, while the RL policy will control the remaining available actuators.

The final action representation will depend on the simulation model and control formulation.

### Reward Function

The reward function will be designed to encourage successful recovery and desirable flight behaviour.

Potential reward components include:

| Reward Component | Purpose |
|---|---|
| Altitude Maintenance | Encourage the vehicle to maintain or recover altitude. |
| Position Objectives | Encourage desired position or trajectory behaviour where applicable. |
| Desired Angular Motion | Encourage appropriate rotational behaviour for the recovery strategy. |
| Instability Penalties | Penalize undesirable states or dangerous motion where appropriate. |
| Control Effort | Encourage efficient actuator usage. |
| Recovery Objective | Reward successful recovery or completion of the defined task. |

The reward function will be refined through experimentation to avoid encouraging undesirable behaviours and to balance recovery objectives.

## Stage 4 — PPO Training

Train the recovery policy using Proximal Policy Optimization.

PPO will be explored as the primary RL algorithm due to its suitability for continuous control tasks and its practical use in training policies for simulated robotic systems.

### Training Focus

- PPO implementation and configuration.
- Policy and value network design.
- Reward function experimentation.
- Observation normalization where applicable.
- Training stability.
- Exploration.
- Episode design.
- Failure timing.
- Training performance.
- Evaluation of learned behaviours.

### Initial Goal

Develop a policy capable of learning recovery behaviour following complete rotor failure within the simulation environment.

## Stage 5 — Evaluation

Evaluate the learned policy using multiple scenarios and metrics.

### Evaluation Metrics

| Metric | Purpose |
|---|---|
| Recovery Success Rate | Measure the proportion of successful recovery episodes. |
| Flight Survival Time | Measure how long the vehicle remains within acceptable flight conditions. |
| Altitude | Evaluate altitude maintenance or recovery. |
| Position Deviation | Evaluate position control where applicable. |
| Angular Velocity | Analyse rotational behaviour. |
| Control Effort | Evaluate actuator usage. |
| Robustness | Assess performance across disturbances and varied conditions. |

### Evaluation Scenarios

- Different failure timings.
- Different initial conditions.
- External disturbances.
- Randomized physical parameters.
- Different recovery states.

## Stage 6 — Robustness & Sim-to-Real Techniques

Investigate simulation-based techniques that can improve the robustness of the learned policy and its potential deployability to real-world systems.

No real-hardware deployment is planned within the scope of this project. Sim-to-Real readiness will instead be investigated through simulation-based experiments.

### Potential Techniques

- Domain randomization.
- Randomized mass and inertia parameters.
- Randomized motor characteristics.
- Thrust variation.
- Disturbance injection.
- Observation noise.
- Actuator dynamics modelling.
- Actuator latency modelling.
- Robustness evaluation across randomized environments.

### Objective

Investigate whether policies trained under varying simulation conditions can generalize across changes in physical parameters and disturbances, improving their potential transferability to real-world systems.

---

# 8. Proposed Experimental Scenarios

| Scenario | Description | Objective |
|---|---|---|
| **Nominal Flight** | Quadrotor operating under normal conditions before rotor failure. | Establish a baseline and validate the simulation. |
| **Single Rotor Failure** | Introduce complete failure of one rotor during flight. | Investigate recovery behaviour under asymmetric thrust. |
| **Recovery from Disturbances** | Introduce disturbances or destabilized initial conditions. | Evaluate recovery under challenging conditions. |
| **Randomized Conditions** | Vary physical parameters across episodes. | Investigate robustness and generalization. |
| **Robustness Evaluation** | Evaluate across different failure timings, initial states and disturbances. | Analyse the reliability of learned recovery behaviour. |

---

# 9. Learning Resources

## 9.1 Research Papers

The research papers listed in Section 4 serve as the primary references for understanding rotor failure, fault-tolerant control, unconventional flight manoeuvres and learning-based recovery.

## 9.2 Video Resources

The following video resources and playlists will be used to build foundational understanding of Reinforcement Learning, robotics, control and related concepts.

### Videos

- [Video 1](https://youtu.be/VnpRp7ZglfA)
- [Video 2](https://youtu.be/bPtiN8MS-LE)
- [Video 3](https://youtu.be/5VHLd9eCZ-w)

### Playlists

- [Stanford CS224R — Deep Reinforcement Learning](https://youtube.com/playlist?list=PLMrJAkhIeNNQe1JXNvaFvURxGY4gE9k74)
- [Playlist 2](https://youtube.com/playlist?list=PLoROMvodv4rPwxE0ONYRa_itZFdaKCylL)
- [Playlist 3](https://youtube.com/playlist?list=PLOkmXPXHDP22VQmr37DFuJr6k30setQ2w)
- [Playlist 4](https://youtube.com/playlist?list=PLYExBrZNJeQg)
- [Playlist 5](https://youtube.com/playlist?list=PLi4fQEV0kn76RSdRrxVwOpiBduSejGhgq)

## 9.3 Documentation

- [MuJoCo Documentation](https://mujoco.readthedocs.io/)
- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)

**Real-hardware deployment is not part of the project scope.** Sim-to-Real readiness will be explored through simulation-based robustness and generalization experiments.

---

*SPIN — Learning to fly differently when flying normally is no longer an option.*
