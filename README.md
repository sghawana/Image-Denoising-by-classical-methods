# Image De-noising and MMSE Estimation

## Overview
This repository contains implementations of various image de-noising techniques and MMSE (Minimum Mean Squared Error) estimation methods. The report includes detailed mathematical formulations and numerical results for different approaches to de-noising images corrupted by Gaussian noise.

## Methods Implemented

### 1. MMSE Estimation for Laplacian Source
- The goal is to estimate the original signal $X$ from a noisy observation $Y$ where:
  - $Y = X + Z$
  - $X \sim \text{Laplacian}(0,\sigma_X)$, $\sigma_X = 1$
  - $Z \sim \text{Gaussian}(0,\sigma_Z)$, $\sigma^2_Z = 0.1$
- The MMSE estimate is computed using:<br>
  $$\hat{X}(y) = \mathbb{E}[X |Y]$$<br>
- Numerical integration is used to solve the final integral.
- Plots are generated for different values of the Laplacian parameter $\alpha$.

### 2. Image De-noising Techniques

#### 2.1. Low-pass Gaussian Filtering
- This method assumes that noise is predominantly present at high frequencies.
- The noisy image is convolved with a Gaussian kernel to obtain a de-noised estimate:<br>
  $$\hat{X}(y) = \mu_Y$$<br>
- MSE (Mean Squared Error) values are computed for different filter sizes and variances.

#### 2.2. MMSE Image De-noising
- The noisy image is modeled as:<br>
  $$Y = X + Z$$<br>
- Assumptions:
  - $Y \sim \text{Gaussian}(0, \sigma_Y)$
  - $X \sim \text{Gaussian}(0, \sigma_X)$
  - $Z \sim \text{Gaussian}(0, \sigma_Z)$, $\sigma_Z = 10$
- The MMSE estimate is computed using:<br>
  $$\hat{X} = \mu_Y + \frac{\sigma^2_X}{\sigma^2_X + \sigma^2_Z} Y_1$$<br>

#### 2.3. Adaptive Shrinkage Estimation
- Utilizes Haar wavelet transform to de-noise images.
- Implements SureShrink thresholding based on the principle:<br>
  $$\hat{X}_1(Y_1) = \text{sgn}(Y_1) \cdot \max(|Y_1| - t, 0)$$<br>

## Results Summary
Please refer to reprt.pdf for results 
