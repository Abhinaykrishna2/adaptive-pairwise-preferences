# Adaptive Pairwise Preferences with Latent Factor Models

## Overview
This repository implements core ideas from  
**"Two of a Kind or the Ratings Game? Adaptive Pairwise Preferences and Latent Factor Models"**  
by Suhrid Balakrishnan and Sumit Chopra.

The project focuses on adaptively learning user latent factors using **sequential pairwise preference feedback** under a **Bayesian framework**, operating over large-scale real-world datasets.

## Dataset
All experiments are conducted on the **full Netflix Prize dataset** (or its equivalent Kaggle movie dataset).

> **Note:** While the original paper also used a proprietary TV viewership dataset,  
> this implementation exclusively uses the public movie dataset, ensuring full reproducibility.

## Project Goals
- Model user preferences through **pairwise comparisons** instead of static ratings.
- **Select feedback pairs adaptively** using **information gain maximization**.
- Perform **sequential Bayesian updates** to refine user parameter estimates.
- Validate the methodology on **large-scale real-world datasets**.

## Approach and Clarifications
This project closely follows the original paper’s methodology with **only one key liberty**:
- **Exact information gain computation** was implemented for selecting item pairs adaptively.
- Bayesian updates were performed after each feedback iteration.
- **Liberty Taken:** Instead of live user feedback, **randomized simulated user responses** were generated based on latent factors to emulate the pairwise choices users would make.

This choice enables experimentation without requiring real-time user input while maintaining the integrity of the sequential learning process.

## Results and Learnings
- Adaptive pairwise feedback shows **faster convergence** in refining user parameters than random questioning.
- The simulated feedback approach enables **large-scale evaluations** of the adaptive selection strategy.
- Handling the **full dataset** validates the **practical scalability** of adaptive Bayesian preference learning.

## Future Work
- Extend the user feedback simulation to more realistic (noisy or biased) models.
- Incorporate **Expectation Propagation (EP)** for more precise Bayesian updates.
- Expand experiments to cover **implicit feedback** settings.
- Compare adaptive pairwise learning vs. traditional explicit ratings on ranking quality metrics (e.g., nDCG, RRMSE).

## References
- Balakrishnan, S., & Chopra, S. (2012). *Two of a Kind or the Ratings Game? Adaptive Pairwise Preferences and Latent Factor Models*. Frontiers of Computer Science, 6(2), 197–208. [DOI: 10.1007/s11704-012-2871-7](https://doi.org/10.1007/s11704-012-2871-7)

## Acknowledgements
- Netflix Prize Dataset (and Kaggle community)
- Inspiration from Balakrishnan & Chopra’s pioneering work on adaptive preference learning
