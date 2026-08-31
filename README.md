# Autonomous Radiation Source Localisation and Estimation using direct path optimisation and particle filtering

This repository contains follow-on research into autonomous radiation source localisation and estimation, conducted during a research internship at The University of Hong Kong (HKU).

The work builds on my [third-year disseration](https://github.com/ChunHeiWongIvan/Reinforcement_Learning) at the University of Manchester, which investigated particle filtering combined with deep reinforcement learning (DQN) for autonomous estimation and seeking of multiple radiation sources.

In this revised approach, the reinforcement learning component was removed and the source-seeking strategy was reformulated around particle filtering and direct optimisation. The aim was to investigate whether autonomous localisation and estimation could be achieved using a simpler optimisation-based approach without requiring a separately trained reinforcement learning policy.

## Approach

The system estimates unknown radiation sources from noisy measurements using a particle filter. The estimated particle distribution is then used to guide the selection of subsequent measurement locations through direct optimisation.

The process consists of:

1. Taking a radiation measurement at the agent's current position.
2. Updating the particle distribution based on the new measurement.
3. Estimating the number, locations, and strengths of the radiation sources.
4. Selecting the agent's next measurement location using direct optimisation.
5. Repeating the estimation and seeking process as further measurements are collected.

## Repository Structure

- `particle_filter.py` – Particle filter implementation for radiation source estimation.
- `direct_optimisation_test_1src.py` – Direct-optimisation approach for a single radiation source.
- `direct_optimisation_test_3src.py` – Extension of the approach to multiple radiation sources.
- `radiation_discrete.py` – Radiation environment, source, and agent definitions.
- `radiation_STE_discrete.py` – Earlier reinforcement-learning-based implementation retained from the original research.
- `multi_source_results/` – Simulation results and generated plots.

## Research Background

The [original project](https://github.com/ChunHeiWongIvan/Reinforcement_Learning) investigated particle filtering with goal-directed deep reinforcement learning for simultaneous radiation source estimation and autonomous source seeking.

This repository represents a subsequent research iteration carried out during my research internship at HKU. The methodology was revised to remove the learned DQN navigation policy and investigate a more direct optimisation-based source-seeking strategy while retaining particle filtering for probabilistic source estimation.

The repository therefore contains both elements of the earlier implementation and the later optimisation-based experiments (E.g. The attached thesis was unchanged from the original). 

## Requirements

- Python 3.9+
- NumPy
- Matplotlib
- Statsmodels
