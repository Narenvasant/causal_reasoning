# Causally-Aware Robot Action Verification

This repository contains the implementation and experiments for the paper
**"Causally-Aware Robot Action Verification via Interventional Probabilistic
Circuits"** (SPAI @ IJCAI 2026).

## Overview

When a robot action plan fails verification, blind resampling is wasteful 
and uninformed. This framework instead triggers **causal diagnosis**: it
identifies which action parameter caused the failure and recommends a
targeted corrective value derived from the interventional distribution —
without retraining, additional data collection, or simulation rollouts.

The system couples **Joint Probability Trees (JPTs)** for motion planning
with a **Causal Circuit** constructed via a Marginal-Deterministic Variable
Tree (MdVtree), enabling exact, polytime computation of interventional
distributions via backdoor adjustment. A pre-deployment support determinism
verification step certifies tractability before the robot begins operating.

## Experiments

All experiments are conducted in a **ROS2 simulation environment** with a
PR2 robot on a geometrically constrained pick-and-place task (5,000
iterations). Two planning conditions are evaluated:

- **High-quality JPT**: success rate improved from 89% to 98.5% (+9.5 pp)
- **Degraded JPT**: failed attempts reduced by 37%, recovery time improved
  by 2.2×, worst-case attempts per iteration reduced from 10 to 3
- **Pick_Place demo** file for both JPT and JPT+Causal extension
- **Run** file to run both the demo simultaneously

## Running Experiments

- The demo files can be run individaully. To run both demos simulataneosly, use the run.py file.


## Requirements

- [CRAM](https://github.com/cram2/cognitive_robot_abstract_machine)
- ROS2 (Humble or later)
- [Joint Probability Trees](https://github.com/joint-probability-trees/jpt-dev)
- Python 3.10+
- numpy
- pandas
- sqlalchemy
- rclpy
