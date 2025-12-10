---
title: "NASA CloudML: Machine Learning for Atmospheric Remote Sensing"
date: 2025-08-15
draft: false
tags: ["Machine Learning", "NASA", "Remote Sensing", "Python", "XGBoost"]
summary: "ML framework for cloud base height retrieval from NASA ER-2 observations. Achieved R²=0.744 using gradient boosting, outperforming CNNs by 130%. NASA GSFC internship."
weight: 3
---

**Status:** Preprint pending journal submission

## Overview

Machine learning framework for cloud base height retrieval from NASA ER-2 airborne observations, comparing feature-based (gradient boosting) versus image-based (CNN) approaches. Demonstrated that **atmospheric features outperform images**, achieving **R² = 0.744** with gradient boosting—a **130% improvement** over CNNs (R² = 0.320).

Developed during my **NASA Goddard Space Flight Center OSTEM internship** (Summer 2025).

## Key Results

| Metric | Value |
|--------|-------|
| Gradient Boosting R² | 0.744 |
| CNN R² | 0.320 |
| Improvement | 130% |
| Labeled Samples | 933 |

## Technical Approach

### Data Pipeline
- **HDF5 preprocessing pipeline** for NASA ER-2 observations
- Temporal interpolation and radiometric correction
- Integration with **ERA5 reanalysis** atmospheric data
- 933 labeled samples across multiple flight campaigns

### Model Comparison
- **Feature-based:** XGBoost gradient boosting with atmospheric variables
- **Image-based:** Convolutional neural networks on raw imagery
- Result: Atmospheric features significantly outperform raw images

### Domain Shift Analysis
- **Leave-one-flight-out cross-validation** to assess generalization
- Identified generalization failure (R² = -1.007 on held-out flights)
- Proposed domain-adversarial solutions for improved robustness

## Application

Cloud base height is critical for:
- Aviation safety and flight planning
- Climate modeling and weather prediction
- Satellite calibration/validation

This work demonstrates that physics-informed features can outperform deep learning on image data when domain expertise is available.

## Technology Stack

- **ML Frameworks:** PyTorch, TensorFlow, scikit-learn
- **Gradient Boosting:** XGBoost, LightGBM
- **Data Processing:** HDF5, NetCDF, Pandas, NumPy
- **Atmospheric Data:** ERA5 reanalysis

## Links

- [GitHub Repository](https://github.com/rylanmalarchick/CloudMLPublic)
- Paper: "Atmospheric Features Outperform Images for Cloud Base Height Retrieval" (pending submission)

## Affiliation

**NASA Goddard Space Flight Center**  
OSTEM Intern – Atmospheric Remote Sensing  
May – August 2025
