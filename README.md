# HFT-Alphas
Exploring DeepLearning models for high frequency trading


# DeepLOB

> **Deep Learning for Limit Order Books**  
> Based on *"Deep Learning for Limit Order Books"* by Zhang et al.

## Overview
DeepLOB is a deep learning architecture designed to predict price movements directly from limit order book (LOB) data. It integrates convolutional and recurrent layers to capture both spatial and temporal patterns in high-frequency market data.

---

## Model Architecture

<p align="center">
  <img src="./2404d3ff-6f65-4e24-8d9d-0bce7e9b4957.png" alt="DeepLOB Architecture" width="600">
</p>

### Three-Stage Deep Learning Model
1. **CNN Layers**  
   - Extract spatial features from the LOB using convolutional filters.
2. **LSTM Layers**  
   - Model temporal dependencies in order book sequences.
3. **Fully Connected Output Layer**  
   - Classify price movement directions.

**Architecture Components:**
- **Input:** Raw LOB data (price levels, order volumes).
- **Convolution Blocks:**  
  - `1x2@16 (stride=1x2)`  
  - `4x1@16`  
  - `4x1@16`
- **Inception Module:**  
  - Parallel convolutions (`1x1@32`, `3x1@32`, `5x1@32`) and max-pooling (`3x1`) followed by concatenation.
- **LSTM Layer:** 64 units.
- **Output Layer:** Classification into upward, downward, or stationary price movement.

---

## Datasets
Two datasets were used for model training and evaluation:

1. **FI-2010 Dataset**  
   - Public benchmark dataset containing simulated high-frequency limit order book data.
   - Widely used in academic research for evaluating LOB prediction models.

2. **Real Market Dataset**  
   - Proprietary dataset from real financial markets, including full-depth order book records.
   - Captures realistic market microstructure patterns and noise.

**Training & Evaluation Approach:**
- Separate models were trained **individually** on each dataset.
- Models were **evaluated on the respective dataset** they were trained on.
- This approach ensures dataset-specific performance metrics without cross-domain leakage.

---

## Performance
The DeepLOB architecture:
- Significantly outperforms traditional statistical models.
- Beats baseline machine learning methods in predicting price movements.
- Achieves high accuracy and robustness in experimental evaluations.

---


## Results Presentation
The enhanced DeepLOB model trained on real market data and the results are avaiable in the presentation attached above
[Presentaion](Presentation.pptx)

---


## Reference
Zhang, Z., Zohren, S., & Roberts, S. (2019). *Deep Learning for Limit Order Books*.  
[arXiv:1808.03668](https://arxiv.org/abs/1808.03668)
