# Multimodal Emotion Recognition with DUAL
This repository presents **DUAL (Dynamic Unified Alignment for Low-text dependency)**, a multimodal emotion recognition model that leverages **audio**, **visual**, and **textual** modalities. Unlike traditional models that rely heavily on text, DUAL prioritizes **audio-visual signals** and introduces text only at the **decoding stage** for semantic refinement, enabling robust performance even under **noisy or missing text** conditions.

## Table of Contents

- [Introduction](#introduction)  
- [Project Goals](#project-goals)  
- [Dataset Information](#dataset information)  
- [Code Information](#code information)  
- [Setup & Dependencies](#setup & dependencies)  
- [Usage Instructions](#usage instructions)  
- [Methodology](#methodology)  
- [Traning](#traning)
- [Results](#results)  
- [Citation](#citation)  
- [License](#license)  
- [Contribution Guidelines](#contribution guidelines)  

---

## Introduction

**DUAL** is designed to improve **multimodal emotion recognition** by reducing reliance on textual input and exploiting the rich **emotional cues** inherent in audio and visual modalities.
Key innovations include:
- **Sentiment Differential Module (SDM)**: captures temporal differences in audio signals.
- **Visual Differential Module (VDM)**: models dynamic visual emotion cues.
- **Sentiment Residual (SR) mechanism**: enhances cross-modal complementarity.
- **Cross-Attention Decoder**: integrates text only for semantic refinement.
This approach ensures higher robustness and adaptability in real-world applications where text may be incomplete, noisy, or unavailable.

---

## Project Goals

- Develop a **low-text dependency** emotion recognition model.
- Prioritize **audio-visual modalities** for emotion understanding.
- Introduce **differential & residual mechanisms** for dynamic and cross-modal modeling.
- Provide a **modular, reusable, and efficient codebase** for research.

---

## Dataset Information
Please download the following datasets into a folder, e.g. /gpfsdswork/dataset/DUAL and unzip:
IEMOCAP dataset (audio, visual, and text dialogues, ~12 GB) from the [IEMOCAP official website].
MELD dataset (multimodal multi-party dialogues with emotion annotations, ~2 GB) from the [MELD official website].
(Optional) Other multimodal benchmarks (aligned audio-visual-text datasets) depending on your experiment setup.
The dataset folder at /gpfsdswork/dataset/DUAL should have the following structure:

```bash
└── /gpfsdswork/dataset/DUAL
    ├── IEMOCAP
    │   ├── Audio
    │   ├── Video
    │   └── Transcriptions
    ├── MELD
    │   ├── train
    │   ├── dev
    │   └── test
    └── OtherDatasets
        └── ...
```
---

## Data

This project uses standard multimodal emotion recognition datasets such as IEMOCAP, MELD, or similar benchmarks. These datasets include aligned audio, video, and text modalities, supporting evaluation of DUAL in diverse emotional contexts.

---

## Model Architecture
DUAL consists of the following key components:

- Audio and Visual Encoders: Extract modality-specific emotional features
- Nonlinear Alignment: Combines features into a shared emotional space
- SDM & VDM: Capture temporal differences in audio/visual emotion cues
- Sentiment Residuals: Cross-modal projections to enhance fusion
- Cross-Attention Decoder: Integrates text only at the decoding stage for refinement
- Multi-part Loss: Combines classification, static, and dynamic alignment losses

---

## Training

To train the model, run:

```bash
python train.py
```
---

## Results

DUAL achieves competitive performance on multiple benchmarks, especially under low-text or noisy-text conditions. Detailed metrics and ablation studies are available in the results/ directory.
