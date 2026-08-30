# Diabetic-Retinopathy
# Drishti — Explainable AI Screening for Diabetic Retinopathy

## Problem
India has over 77 million diabetic adults, and nearly 18% develop diabetic retinopathy (DR) — a leading cause of preventable blindness. Early screening can prevent up to 90% of DR-related vision loss, but rural India has only about 1 ophthalmologist per 100,000 people, making timely screening largely inaccessible. Existing AI screening tools compound this gap by functioning as unexplainable "black boxes" and by performing poorly on the variable-quality images typical of low-cost, portable field cameras.

## Solution
Drishti is an explainable AI screening system designed for real deployment in primary healthcare centres and rural health camps, not just a lab demo. It:

- Assesses and enhances fundus image quality before analysis, rejecting unusable images with recapture feedback
- Segments retinal structures and detects disease markers — microaneurysms, hemorrhages, exudates, neovascularization
- Classifies DR severity on the standard International Clinical DR Severity Scale (Levels 0–4)
- Generates Grad-CAM heatmaps and structured, lesion-level explainability reports so a healthcare worker can verify results in under 30 seconds
- Automatically escalates low-confidence cases for mandatory human review instead of guessing
- Communicates results to patients in plain, multilingual language
- Demonstrates field deployability through a low-cost smartphone-and-lens capture prototype

## Status
This repository is in active development. Current focus: training and validating the core classification pipeline against public clinical benchmark datasets before integrating the full application layer.

## Tech Stack
- **Model:** Python, TensorFlow/PyTorch — CNN-based DR classifier
- **Explainability:** Grad-CAM, structured lesion-level reporting
- **Backend:** Flask
- **Frontend:** React (mobile-responsive PWA, offline-capable)
- **Database:** SQLite / Firebase
- **Datasets:** APTOS 2019, IDRiD, Messidor-2 (public, clinically labeled)
- **Field hardware:** Smartphone + ophthalmic lens attachment + LED illumination, EEG graphene Electrode for capturing brain signals

## Exploratory Research Extension
As a separate, clearly-labeled research direction — not part of the core validated system — we are collecting preliminary Visual Evoked Potential (VEP) data to explore whether early functional neural changes might precede visible structural retinal damage. This module runs independently and does not feed into the core DR severity grading or confidence scoring.

## Validation Approach
Model accuracy is benchmarked against public clinical datasets, not against images captured by our own field prototype — these two claims are deliberately kept separate. The field-capture device demonstrates deployment feasibility; it is not the source of our reported accuracy figures.

## Disclaimer
This is a screening aid intended to support, not replace, clinical judgment. It has not undergone clinical validation or regulatory approval and is not intended for standalone diagnostic use.

## Team
[Spartix]

## References
- APTOS 2019 Blindness Detection Dataset (Kaggle)
- IDRiD (Indian Diabetic Retinopathy Image Dataset)
- Messidor-2 Dataset
- [Add citations for vessel segmentation and AI+IoT remote screening papers referenced during research]
