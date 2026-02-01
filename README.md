# Multimodal Disaster Classification

Implementation of **"Zero-Shot Social Media Crisis Classification: A Training-Free Multimodal Approach"**.

> **Paper status:** Manuscript in preparation for submission to Applied Sciences (MDPI).  
> This README will be updated with full citation details upon publication.

## Overview

This repository contains a single Jupyter notebook that implements zero-shot multimodal classification for disaster-related social media content using the Mistral-Small-3.1-24B-Instruct model.

## Performance

| Task                  | Modality | F1 Score | Accuracy |
| --------------------- | -------- | -------- | -------- |
| Informativeness       | Text     | 0.8415   | 78.3%    |
| Informativeness       | Image    | 0.8417   | 83.1%    |
| Humanitarian Category | Text     | 0.6106   | 61.0%    |
| Humanitarian Category | Image    | 0.7213   | 71.4%    |

## Usage

### Requirements

- Google Colab with A100 GPU runtime (40GB VRAM)
- The notebook uses 25-27 GB GPU memory during operation

### Instructions

1. **Open in Google Colab**
   - Click: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nored/multimodal-disaster-classification/blob/main/disaster_classification.ipynb)

2. **Set Runtime**
   - Go to `Runtime` → `Change runtime type`
   - Select `A100 GPU` as hardware accelerator

3. **Run the Notebook**
   - Execute all cells sequentially
   - First run will download:
     - Mistral-Small-3.1-24B model (~25GB)
     - CrisisMMD dataset (~2GB)
   - Total runtime: ~2-3 hours for full dataset

4. **Results**
   - All results are saved in `/content/llama.cpp/results/`
   - Download the results zip file when prompted

## What the Notebook Does

1. **Setup**: Installs dependencies and builds llama.cpp with CUDA support
2. **Model Download**: Downloads quantized Mistral-Small model and multimodal projector
3. **Data Preparation**: Downloads and extracts CrisisMMD dataset
4. **Server Launch**: Starts llama.cpp inference server
5. **Classification**: Processes all 18,082 tweet-image pairs
6. **Evaluation**: Calculates F1 scores and generates confusion matrices
7. **Output**: Creates downloadable results package

## Dataset

The notebook automatically downloads the CrisisMMD dataset containing:

- 18,082 tweet-image pairs from 7 disasters
- Binary informativeness labels
- 8 humanitarian categories
- Separate annotations for text and images

## Authors

Franziska Schwarz, Klaus Dieter Schwarz, Daniel Arias Aranda, Kendrick Bollens, Navaneeth Shivananjappa, Reiner Creutzburg, Vesna Dimitrova

## Citation

Citation details will be added once the paper is published. In the meantime, if you use this code, please reference this repository:

```
Schwarz, F., Schwarz, K.D., Arias Aranda, D., Bollens, K., Shivananjappa, N.,
Creutzburg, R., & Dimitrova, V. (2026). Zero-Shot Social Media Crisis Classification:
A Training-Free Multimodal Approach. [Manuscript in preparation].
```
