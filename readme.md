# RPQNet - Super Resolution Optimization

## Overview

This project investigates the RPQNet_WSDR_EV2 super resolution network through floating point training, model collapsing, quantization and pruning. The impact of these optimization techniques on model complexity, computational cost and image reconstruction quality is evaluated using PSNR, FLOPs and parameter analysis.

## Objectives

* Train RPQNet_WSDR_EV2 for image super resolution.
* Compare RGB and Y channel only training approaches.
* Evaluate the effects of model collapsing on efficiency and output quality.
* Apply and compare Post-Training Quantization (PTQ) and Quantization-Aware Training (QAT).
* Investigate unstructured and layer-wise pruning techniques.
* Analyze the trade-offs between model compression and reconstruction performance.

## Features

### Floating Point Training

* RGB model training and evaluation
* Y channel only model training and evaluation
* PSNR validation metrics
* Super resolution image visualization

### Model Analysis

* Parameter count comparison
* Floating point operations (FLOPs) analysis
* Model collapsing
* MSE comparison between original and collapsed models

### Pruning

* Iterative magnitude-based unstructured pruning and fine-tuning
* Layer-wise sensitivity analysis, pruning and fine-tuning
* PSNR and visual comparison

### Quantization

* Per-tensor PTQ
* Per-channel PTQ
* Per-tensor QAT
* Per-channel QAT
* PSNR and visual comparison

## Results Summary

### Float Training

* Successfully trained RGB and Y channel only models.
* The Y channel only model achieved higher validation PSNR than the RGB model.
* Y channel training reduced input/output dimensionality while maintaining strong reconstruction quality.

### Model Collapsing

* Collapsed models produced outputs nearly identical to the original networks.
* Inference complexity was reduced while preserving image quality.

### Pruning

* Unstructured pruning reduced parameter usage while maintaining acceptable performance after fine-tuning.
* Layer-wise sensitivity analysis identified layers that were more tolerant to pruning.
* Layer-wise pruning provided a more targeted compression strategy.

### Quantization

* PTQ introduced a noticeable PSNR decrease.
* QAT recovered a significant portion of the lost performance.
* The Y channel only model showed a larger difference between per-tensor and per-channel quantization, indicating greater sensitivity to quantization granularity.

## Conclusion

The experiments demonstrate that RPQNet_WSDR_EV2 is an efficient super resolution architecture that can be further optimized through collapsing, pruning and quantization. While increasing efficiency generally introduces some loss in reconstruction quality, careful optimization enables deployment on resource-constrained hardware while maintaining strong super resolution performance.
