# Machine Learning-Assisted Binding Site Selection

Supervised machine learning for descriptor-based classification and
prioritization of candidate binding sites identified through fragment
dissolved Gaussian accelerated molecular dynamics (fdGaMD) simulations.

## Overview

Identifying the most plausible binding site from molecular dynamics
simulations often requires the combined interpretation of multiple
descriptors. Although these descriptors provide complementary information,
their manual assessment can become challenging when several candidate
sites exhibit similar profiles.

This project explores machine learning as a decision-support strategy
within the fragment dissolved molecular dynamics (fdMD) framework.
Simulation-derived descriptors are combined to distinguish binding sites
corresponding to an experimental reference from alternative sites
identified during the simulations.

The objective is to support binding site prioritization while reducing
reliance on the manual interpretation of individual descriptors.

## Dataset

The initial benchmark comprises:

- 12 ligand–protein systems.
- 102 candidate binding sites.
- 14 sites labeled as native.
- 88 sites labeled as non-native.

Each entry represents a candidate binding site characterized by
descriptor-based analysis of fdGaMD simulations.

Sites are labeled according to their correspondence with the
experimentally observed binding site:

- Native: a site corresponding to the experimental reference.
- Non-native: an alternative site relative to that reference.

The non-native label does not establish that binding at an alternative
site is physically impossible.

The prediction task concerns binding site identity, not binding
affinity or biological activity.

## Machine Learning Approach

The workflow uses supervised binary classification to distinguish
native from non-native candidate sites.

A Random Forest classifier provides the baseline model, with class
balancing used to address the unequal representation of the two classes.

Candidate sites are prioritized within each ligand–protein system
using the predicted probability of belonging to the native class:

1. Characterize each candidate site using simulation-derived descriptors.
2. Apply the classifier to obtain native-class probabilities.
3. Rank candidate sites within each system.
4. Select the highest-ranked site for further assessment.

These probabilities are classifier outputs, not thermodynamic binding
probabilities. Because candidate sites are classified individually,
their probabilities are not constrained to sum to one within a system.

## Validation and Evaluation

Model evaluation uses leave-one-group-out cross-validation (LOGOCV),
with each ligand–protein system treated as a separate group.

At each iteration, all candidate sites from one system are held out
for testing, while the remaining systems are used for training.
Candidate sites from the same system therefore do not appear in both
the training and test sets within a fold.

The primary evaluation metric is system-level Top-1 accuracy:
the fraction of held-out systems for which the highest-ranked
candidate corresponds to a native binding site.

Site-level classification metrics provide complementary information
about discrimination between native and non-native sites.

## Scope and Limitations

This project is an exploratory study based on a small, imbalanced
dataset. Its purpose is to assess whether simulation-derived
descriptors can support binding site prioritization.

Performance on this benchmark should not be interpreted as evidence
of general applicability to arbitrary targets or ligands.

Predictions depend on the candidate sites sampled during the
simulations and on the descriptors used to characterize them.
The classifier cannot identify an experimental binding site that
is absent from the candidate set.

The workflow supports, rather than replaces, structural inspection
and scientific assessment of the proposed binding sites.

## Documentation and Reproducibility

Documentation accompanying the released code and data will describe:

- Input data and descriptor definitions.
- Class labels and system identifiers.
- Data preprocessing.
- Model configurations and random seeds.
- Cross-validation and evaluation procedures.
- Software requirements.
- Instructions for reproducing the analyses.

## Acknowledgments

This work was developed during a research stay at the AI Laboratory
for Molecular Engineering (AIME), within the Data Science and
Artificial Intelligence division at Chalmers University of Technology,
Gothenburg, Sweden, under the supervision of Dr. Rocío Mercado Oropeza.

The research stay was supported by the PREDOCS-UB fellowship program.

## Citation

Publication details and citation instructions will be added soon.
