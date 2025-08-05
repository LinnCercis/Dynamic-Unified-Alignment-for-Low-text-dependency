# Multimodal Emotion Recognition with DUAL
This project presents a multimodal emotion recognition model using audio, visual, and textual data. The proposed DUAL model emphasizes low-text dependency by prioritizing audio-visual features and introducing text only at the decoding stage for semantic refinement.
Table of Contents
Introduction
Project Goals
Setup Instructions
Data
Model Architecture
Training
Results
License
Introduction
Welcome to the DUAL Project! This project introduces DUAL (Dynamic Unified Alignment for Low-text dependency), a multimodal emotion recognition model designed to reduce reliance on textual input while leveraging rich emotional cues from audio and visual modalities.
Unlike traditional models that depend heavily on text, DUAL focuses on nonlinear alignment of audio and visual features to form a unified emotional representation. It introduces key innovations such as the Sentiment Differential Module (SDM) and Visual Differential Module (VDM) to capture temporal emotional dynamics, and a Sentiment Residual (SR) mechanism to enhance cross-modal complementarity. Text is integrated only during decoding via a cross-attention module, refining predictions with minimal text reliance.

This design improves performance in scenarios where text is noisy, missing, or secondary—paving the way for more robust, real-world emotion recognition systems.

Project Goals
Develop a multimodal emotion recognition model with low text dependency.
Emphasize the use of audio and visual modalities for emotion understanding.
Introduce novel differential and residual modules for temporal and cross-modal modeling.
Provide an efficient and reusable codebase for emotion recognition research.
Setup Instructions
To set up the project locally:
Clone the repository:
git clone https://github.com/yourusername/dual-emotion-recognition
Create and activate a conda environment:
conda create -y --name dual python=3.9  
conda activate dual
Install dependencies:
pip install -r requirements.txt
Run the model:
python main.py
Data
This project uses standard multimodal emotion recognition datasets such as IEMOCAP, MELD, or similar benchmarks. These datasets include aligned audio, video, and text modalities, supporting evaluation of DUAL in diverse emotional contexts.
(You can update this section with your actual dataset info and preprocessing notes.)

Model Architecture
DUAL consists of the following key components:
Audio and Visual Encoders: Extract modality-specific emotional features.
Nonlinear Alignment: Combines features into a shared emotional space.
SDM & VDM: Capture temporal differences in audio/visual emotion cues.
Sentiment Residuals: Cross-modal projections to enhance fusion.
Cross-Attention Decoder: Integrates text only at the decoding stage for refinement.
Multi-part Loss: Combines classification, static, and dynamic alignment losses.
Training
Train the model with:
python train.py
Configuration settings (e.g., dataset path, batch size, learning rate) can be adjusted in config.yaml.
Results
DUAL achieves state-of-the-art or competitive performance across several benchmark datasets, especially in low-text or noisy-text conditions. Detailed results and ablations are included in the results/ directory.
