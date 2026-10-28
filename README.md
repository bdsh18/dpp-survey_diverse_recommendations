# Research Survey Proposal

## Determinantal Point Processes for Diverse Recommendations: Quality–Diversity Modelling, Kernel Learning, and Inference

**Status:** Initial proposal for feedback, awaiting final scope approval.

## Aim

I propose to survey determinantal point processes (DPPs) for selecting relevant and diverse recommendation sets.
The survey will connect foundational models, kernel-learning methods, and inference algorithms across literature from 2011 to 2022.
It will compare their assumptions, mathematical properties, computational costs, and limitations.

News recommendation will provide a running example.
Several relevant articles can cover the same event, making a recommendation list repetitive.
The example will illustrate set-level diversity without restricting the reading to news applications.

## Research questions

1. How do DPP kernels represent quality and similarity, and what notion of diversity do they encode?
2. How do fixed-size DPPs control the number of selected items?
3. How do researchers learn kernels, and what restrictions follow from low-rank models?
4. How do sampling and maximum a posteriori (MAP) selection differ in objectives, algorithms, and guarantees?
5. What do published results establish about relevance, diversity, and computational cost?

## Mathematical and algorithmic scope

The core will cover finite DPPs, positive semidefinite kernels, determinant geometry, and the L-ensemble probability model.
For a candidate set V and subset Y, the starting model is:

```text
P(Y) = det(L_Y) / det(I + L), with L positive semidefinite.
L_ij = q_i * S_ij * q_j.
```

Here, L_Y is the principal submatrix for Y.
The terms q_i represent quality, while S represents similarity.
I will examine the assumptions needed for this decomposition and explain its geometric interpretation.
Selected derivations will cover normalisation, quality–similarity decomposition, and fixed-size conditioning.

The learning section will compare low-rank factorisation and other kernel-learning approaches.
The inference section will distinguish sampling from MAP selection.
It will compare fixed-size sampling, kernel approximation, and accelerated greedy MAP algorithms.
The discussion will separate tractable probability calculations from the difficulty of exact MAP optimisation.

Nonsymmetric kernels and sequential recommendation will provide bounded extensions, subject to feedback.
Their assumptions will be treated separately from the symmetric positive semidefinite model above.
Continuous point processes, deployment engineering, and building a complete recommender fall outside the proposed scope.

## Literature map and initial bibliography

This is a proposed reading set, not a claim of completed reading.
The final selection will target 10–15 substantial references after feedback.
Preprint dates are identified explicitly.

### Foundations

1. **Kulesza and Taskar (2011).** [k-DPPs: Fixed-Size Determinantal Point Processes](https://icml.cc/2011/papers/611_icmlpaper.pdf). ICML. Fixed-size subset modelling.
2. **Kulesza and Taskar (2012).** [Determinantal Point Processes for Machine Learning](https://arxiv.org/abs/1207.6083). Foundations and Trends in Machine Learning. Foundational monograph supporting the mathematical treatment.

### Learning and model extensions

3. **Gartrell, Paquet, and Koenigstein (2016 preprint).** [Low-Rank Factorization of Determinantal Point Processes for Recommendation](https://arxiv.org/abs/1602.05436). Compact recommendation kernels.
4. **Dupuy and Bach (2018).** [Learning Determinantal Point Processes in Sublinear Time](https://proceedings.mlr.press/v84/dupuy18a.html). AISTATS. Efficient kernel learning.
5. **Gartrell et al. (2019 preprint).** [Learning Nonsymmetric Determinantal Point Processes](https://arxiv.org/abs/1905.12962). A model extension for comparison.
6. **Liu, Walder, and Xie (2022).** [Determinantal Point Process Likelihoods for Sequential Recommendation](https://arxiv.org/abs/2204.11562). SIGIR. Recommendation objectives using DPP likelihoods.

### Inference, sampling, and approximation

7. **Affandi et al. (2013).** [Nyström Approximation for Large-Scale Determinantal Processes](https://proceedings.mlr.press/v31/affandi13a.html). AISTATS. Kernel approximation.
8. **Li, Jegelka, and Sra (2016).** [Efficient Sampling for k-Determinantal Point Processes](https://proceedings.mlr.press/v51/li16f.html). AISTATS. Fixed-size sampling.
9. **Anari, Oveis Gharan, and Rezaei (2016).** [Monte Carlo Markov Chain Algorithms for Sampling Strongly Rayleigh Distributions and Determinantal Point Processes](https://proceedings.mlr.press/v49/anari16.html). COLT. Sampling guarantees.
10. **Chen, Zhang, and Zhou (2018).** [Fast Greedy MAP Inference for Determinantal Point Process to Improve Recommendation Diversity](https://proceedings.neurips.cc/paper/2018/hash/dbbf603ff0e99629dda5d75b6f75f966-Abstract.html). NeurIPS. Greedy MAP acceleration and recommendation evidence.
11. **Dereziński (2019).** [Fast Determinantal Point Processes via Distortion-Free Intermediate Sampling](https://proceedings.mlr.press/v99/derezinski19a.html). COLT. Faster sampling methods.

The intended narrative is: foundations → kernel learning → subset selection → recommendation extensions.
Sampling theory will support the comparison, while recommendation modelling and inference remain the main focus.

## Published empirical evidence

This is a literature survey. It will not include new experiments, reproduced benchmarks, or system development.
For empirical papers, I will record datasets, baselines, relevance metrics, diversity definitions, runtime measurements, and reported limitations.
The report will distinguish theoretical guarantees from experimental observations.
Results from different datasets or evaluation settings will not be treated as directly comparable scores.
Small hand-worked examples will explain mathematics rather than provide experimental evidence.

## Planned outputs

- A short report connecting the literature, with selected derivations and algorithm comparisons.
- A comparison table covering assumptions, learning objectives, computational costs, guarantees, and published evidence.
- A presentation explaining the main developments and limitations.
- Preparation to explain and defend the mathematical arguments during the viva.

## Prerequisites and provisional schedule

Prerequisites include determinants, eigenvalues, positive semidefinite matrices, conditional probability, optimisation, and algorithm analysis.
These will be reviewed alongside the foundational readings.
This schedule is provisional and remains subject to scope approval and feasibility review.

| Period | Planned work |
|---|---|
| 28 October–2 November 2026 | Review prerequisites and foundations; refine scope after feedback. |
| 3–9 November 2026 | Read learning and inference papers; build technical notes and the literature map. |
| 10–15 November 2026 | Compare published evidence and draft the report. |
| 16–19 November 2026 | Revise the report, prepare slides, and practise derivations and viva questions. |

The first checkpoint is explaining the basic probability model and fixed-size conditioning independently.
Reading depth and scope will be reassessed at that checkpoint.

## Feedback requested

I would appreciate feedback on the balance between kernel learning and inference.
Please advise whether nonsymmetric models or sequential recommendation should be reduced to keep the survey focused.
