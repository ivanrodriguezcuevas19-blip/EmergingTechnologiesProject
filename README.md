# Network Intrusion Detection: A Two-Stage AutoML Pipeline

AIDI 1010 - Group 9
## Overview

This project builds a two-stage machine learning pipeline to help SOC (Security Operations Center) analysts detect and triage network intrusions. Instead of flooding analysts with alerts, the pipeline first flags whether traffic is an attack at all, then classifies what kind of attack it is, so responses can be prioritized.

## Team

- Joao Pedro Schneidr Perondi
- Sehdev Singh
- Ivan Rodriguez Cuevas

## Problem Statement

SOC analysts are overwhelmed by high volumes of network traffic alerts, many of which are false positives. This project explores whether an AutoML-based pipeline can reliably detect intrusions and classify attack types, reducing alert fatigue while surfacing explainable, actionable results.

## Approach

1. **Data & feature engineering** — cleaning and preparing the network traffic dataset
2. **Stage 1: Binary detection** — an AutoML model (MLJAR) flags traffic as attack vs. benign
3. **Threshold selection** — tuned on a validation set, evaluated once on test
4. **Stage 2: Attack classification** — a second model identifies the type/family of attack
5. **Explainability** — SHAP is used to generate per-alert explanations so results are interpretable, not just accurate
6. **Evaluation** — results are compared against three peer-reviewed research papers and against our own prior assignments (prototype vs. final)

## Key Findings

- Careful evaluation (fixing test-set leakage and correcting a test-tuned threshold) improved results more than additional AutoML search time did
- Cross-validation must be done correctly when combined with oversampling (e.g. SMOTENC), doing it in the wrong order can produce badly inflated, misleading metrics
- SHAP-based feature importance sometimes contradicted our own intuitions about which engineered features would matter most

## Repository Contents

- `GRP9_Assignment3_Network_Intrusion_Detection.ipynb` — full project notebook (data prep, modeling, evaluation, explainability, and write-up)

## How to Run

1. Open the notebook in Google Colab or Jupyter
2. Run cells sequentially from Section 0 (Setup) onward
3. Sections are numbered and documented inline; see the notebook's header documentation for problem statement, challenges, and value proposition

## Conceptual Enhancement

This project also discusses how the solution could evolve with advances in AGI (see Section 11 of the notebook).

## Acknowledgments

Built with reference to three peer-reviewed research papers (see References section in the notebook) and course materials from AIDI 1010, Georgian College.
