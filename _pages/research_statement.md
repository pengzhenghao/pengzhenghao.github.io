---
layout: page
permalink: /research/
title: Research Statement
description: Zhenghao Peng, Aug 17, 2025
nav: true
nav_order: 2
---


<style>
.float-right-40 { float: right; width: 40%; margin-left: 1.5em; margin-bottom: 0.5em; }
.float-right-40 figure { width: 100%; margin: 0; }
.float-right-40 img { width: 100%; height: auto; display: block; }

.float-right-30 { float: right; width: 30%; margin-left: 1.5em; margin-bottom: 0.5em; }
.float-right-30 figure { width: 100%; margin: 0; }
.float-right-30 img { width: 100%; height: auto; display: block; }
</style>



{% include figure.liquid zoomable=1 avoid_scaling=1 loading="eager" path="assets/img/RS-Intro.png" class="img-fluid rounded" caption="<b>I like playing with real robots!</b>" %}


### Road to Physical AI

My research aims to build foundation models for robotics that are scalable, aligned, and deployable in the real world. The overarching vision is to endow embodied agents with the understanding of the world and the ability to execute basic skills, align with human intent, and continuously adapt in open-ended environments. 


As shown in the figure below, I organize this agenda into three complementary stages: 

1. Imitation learning pretraining, 
2. Closed-loop post-training, and
3. Human-in-the-loop test-time adaptation.


{% include figure.liquid zoomable=1 avoid_scaling=1 loading="eager" path="assets/img/Framework.png" class="img-fluid rounded z-depth-1" caption="<b>Road to Physical AI:</b> The capacities of physical AI agent are acquired via pretraining, closed-loop finetuning, and  human-in-the-loop test-time adaptation. Important problems in each stage are listed." %}



<br>

### Imitation Learning Pretraining

Imitation learning provides the foundation for physical AI. My recent work focuses on Vision-Language-Action (VLA) pretraining to endow models with embodied understanding and action–language alignment.

In MetaVQA, we constructed datasets to provide 3D grounding and physical reasoning to VLAs.

Currently, I am exploring methods to ensure actions produced by the model are semantically meaningful and physically grounded, enabling reasoning about both execution and consequences.


<br>

### Closed-loop Post-Training: Simulation and RL

<div class="float-right-30">
{% include figure.liquid loading="eager" path="assets/img/RS-Simulation.png" class="img-fluid rounded"%}
</div>


While imitation learning offers strong initialization, open-loop behavior cloning often fails in real deployments. Closed-loop post-training bridges this gap.

**Simulation platforms**: I built MetaDrive and ScenarioNet, enabling large-scale data-driven simulation.
MetaDrive has received 1,000+ GitHub stars and 350+ citations, becoming a widely used benchmark in the community.

**Improving realism**: SceneGen (Diffusion models) and Vid2Sim (3D Gaussian Splatting) rerender visual environments from real videos, creating photorealistic RL environments.

**Data-driven training environments generation**: CAT and SCGEN generate adversarial driving scenarios.
InfGen augments dynamic multi-agent traffic situations.

**Closed-loop finetuning**: I demonstrated in my Waymo paper that reinforcement learning can substantially improve performance when models are tested in feedback-driven settings.

I am exploring the embodied reasoning as a new way to improve VLA.

<br>

### Human-in-the-Loop Test-Time Adaptation


<div class="float-right-40">
{% include figure.liquid loading="eager" path="assets/img/RS-Experiment.png" class="img-fluid rounded" caption="Our method exhibits unprecedented learning efficiency: agents achieve higher performance with significantly fewer data in real-human experiments." %}
</div>


Even with large-scale simulation and RL, agents inevitably face a sim-to-real gap when deployed. Closing this gap requires humans in the loop, providing real-time interventions and feedback to align the agent’s behavior with human values.

Over the years, I have pioneered this research direction with 5 papers. Key contributions:

* EGPO (CoRL 2021): Introduced expert-guided policy optimization using teacher interventions.
* HACO (ICLR 2022): Substituted expert with real human feedback, achieving faster adaptation.
* TS2C (ICLR 2023): Used value function–based intervention to improve teacher–student shared control.
* Proxy Value Propagation (NeurIPS 2023 Spotlight): Addressed reward-free adaptation, reducing oscillations and catastrophic forgetting.
* PVP4Real (ICRA 2025): Deployed PVP on real robots, showing adaptation within 15 minutes of human interaction.

This line of work establishes test-time post-training as the final stage of robotic learning: a continual feedback loop where human guidance ensures safety, adaptability, and alignment.

One interesting direction I want to explore is to human-AI shared control. With the collaboration in teams Jonathan Kao, we have successfully demonstrated that


<br>

### Outlook

By integrating the three stages—foundation model pretraining, closed-loop reinforcement learning, and human-in-the-loop test-time adaptation—my research lays the groundwork for scalable and trustworthy embodied AI.

My long-term goal is to build robots that serve as capable, adaptive, and aligned partners, advancing human well-being in domains such as autonomous driving, assistive robotics, and everyday human–robot interaction.

