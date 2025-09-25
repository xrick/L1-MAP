# L1-MAP: An L1-Aware, Multilingual Framework for Automated Pronunciation Assessment

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/release/python-380/)

This repository contains the official implementation for **L1-MAP**, an end-to-end, multilingual model for automated pronunciation assessment. The framework is designed to provide fine-grained diagnostic feedback on non-native speech, considering the speaker's native language (L1) to deliver more accurate and personalized evaluations.

## 📌 Abstract

Computer-Aided Pronunciation Training (CAPT) systems are vital for self-directed language learning. This project addresses key challenges in the field—data scarcity, modeling difficulty, and evaluation complexity—by proposing a unified, multilingual framework. L1-MAP leverages a pre-trained Self-Supervised Learning (SSL) model (e.g., wav2vec 2.0) as its core and employs a multi-task learning objective to concurrently evaluate both segmental (phonetic) and supra-segmental (prosodic, fluency) features of non-native speech.

## ✨ Key Features

* **Multilingual:** Designed to work across diverse L1-L2 language pairs.
* **L1-Aware:** Incorporates native language information to model specific error patterns, leading to more accurate diagnoses.
* **Multi-Task Learning:** Jointly predicts phoneme-level errors (substitution, deletion, insertion) and utterance-level scores for fluency, prosody, and intelligibility.
* **Data Augmentation:** Includes a pipeline for generating synthetic mispronunciations to combat data scarcity, inspired by the SpeechBlender framework.

## 🏛️ System Architecture

The model is built upon a powerful, pre-trained SSL model which serves as the core acoustic encoder. This foundation is enhanced with two key components:

1.  **L1-Aware Input Layer:** An embedding layer encodes the speaker's L1, and this representation is fused with the speech features.
2.  **Multi-Task Prediction Heads:**
    * **Segmental Diagnosis:** A Connectionist Temporal Classification (CTC) head predicts the phoneme sequence.
    * **Supra-segmental Scoring:** A regression head predicts sentence-level scores for fluency and prosody.



## ⚙️ Installation

To get started, clone the repository and set up the Conda environment.

```bash
# 1. Clone the repository
git clone [https://github.com/your-username/L1-MAP.git](https://github.com/your-username/L1-MAP.git)
cd L1-MAP

# 2. Create and activate the Conda environment
conda env create -f environment.yml
conda activate l1-map

# 3. (Optional) If not using environment.yml, install dependencies
pip install -r requirements.txt
