# Homework 13 — World Models in FrozenLake

This repository contains my solution for **Homework 13** of the master's course **Selected Research Topics in AI**.

## Topic

This project studies whether a **Vision-Language Model (VLM)** can be used not only as a reactive policy, but also as a **world model** that predicts environment dynamics and supports planning.

The setup is based on **FrozenLake**, where the project compares:

- a **reactive zero-shot VLM agent**,
- a **greedy planner with ground-truth state information**,
- **SFT-trained world models**,
- and **lookahead planning** that queries a VLM to imagine the outcome of candidate actions.

## Homework scope

The homework is organized into three main parts:

1. **Reactive agent baseline**
   - zero-shot VLM used directly as a policy,
   - baseline success rate and format compliance,
   - comparison with a greedy planner using perfect state information.

2. **Learning a world model**
   - build a dataset of transitions in FrozenLake,
   - train models to predict next position and outcome,
   - compare image-only vs image + ground-truth text inputs,
   - analyze whether the bottleneck is perception or dynamics understanding.

3. **Planning in imagination**
   - use the trained model as an external imagination engine,
   - perform 1-step lookahead planning,
   - compare reactive, zero-shot lookahead, SFT-based lookahead, and ground-truth planning.

## Current status

This repository is the initial public submission link for the homework.

Implementation, experiments, plots, and full report are being added in subsequent commits.

## Report

The report is available here:

[docs/report.md](docs/report.md)

## Planned contents

This repository is expected to contain:

- FrozenLake data generation code,
- reactive and planning baselines,
- SFT training pipeline for world-model prediction,
- evaluation scripts and metrics,
- plots / tables,
- a structured report with conclusions and limitations.

## Notes

The repository may continue to evolve after the initial submission deadline as the implementation and analysis are finalized.
