# Homework 13 Report — World Models in FrozenLake

## Status

This report is currently in progress.

This repository was created as the initial public submission for Homework 13 of the course **Selected Research Topics in AI**.

The full report will be expanded with implementation details, experiments, plots, and conclusions.

---

## Problem statement

This homework studies whether a VLM can be used as a **world model** for planning in a simple environment.

Instead of predicting the next action directly, the model is asked to predict the **outcome of an action**:
- next position,
- and environment outcome such as `safe`, `hole`, `goal`, or `wall`.

The central question is whether such predictions are good enough to improve control through external planning.

---

## Planned report structure

### 1. Setup

- environment: FrozenLake,
- dataset generation protocol,
- action and outcome format,
- train/validation split by map seeds,
- model choice and prompting format,
- evaluation metrics.

### 2. Part 1 — Reactive baseline

Goal:
evaluate how far a zero-shot reactive VLM can go without explicit learning of dynamics.

Planned evaluation:
- success rate,
- format compliance,
- comparison with a greedy planner using ground-truth transitions.

### 3. Part 2 — Learning a world model

Goal:
train models that predict next state and outcome from current observation and action.

Planned comparison:
- image-only input,
- image + ground-truth state text input.

Main question:
is the main bottleneck **perception** or **understanding of environment dynamics**?

Planned metrics:
- one-step prediction accuracy,
- confusion matrix over outcomes,
- format errors,
- train/validation comparison.

### 4. Part 3 — Planning in imagination

Goal:
evaluate whether external planning based on model predictions improves performance.

Planned conditions:
- reactive baseline,
- lookahead with zero-shot VLM,
- lookahead with SFT image + text model,
- lookahead with SFT image-only model,
- lookahead with ground-truth dynamics.

Planned metrics:
- success rate,
- average number of steps,
- fraction of failures by falling into holes,
- optional confidence intervals.

### 5. Interpretation

The final version of the report will discuss:
- whether lookahead improves over reactive control,
- whether model quality or planning quality is the main bottleneck,
- where the model fails,
- and what these failures suggest about current world-model use in VLM agents.

### 6. Bonus directions

Possible extensions:
- multi-step lookahead,
- chain-of-thought planning inside one prompt,
- comparison between 4×4 and 8×8 maps.

### 7. Conclusions

The final report will summarize:
- what worked,
- what did not work,
- what the main bottlenecks were,
- and what future improvements seem most promising.

---

## Immediate next steps

- implement FrozenLake data generation,
- define prediction format and parser,
- build a reactive baseline,
- train first SFT world-model baselines,
- run the first lookahead evaluation,
- expand this report with real results.
