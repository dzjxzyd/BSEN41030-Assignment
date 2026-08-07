# Barley germination image classification dataset

## What is this dataset?

This dataset follows individual malting-barley kernels during germination. Each kernel was imaged before moisture was added and then once every 24 hours for five days. At each imaging session, a human expert labelled every kernel as **germinated** or **not germinated** from the RGB image.

The dataset includes paired RGB and near-infrared hyperspectral (NIR-HSI) image data, segmentation masks, and derived NIR spectra. It is intended to support modelling of barley germination from image or spectral measurements.

## Dataset size

The retained dataset contains **2,242 individual barley kernels** from **90 Petri dishes**, spanning two samples each of the Prospect and Laureate varieties. Every kernel was recorded at **six time points** (before moisture exposure and Days 1–5), giving **13,452 kernel-time-point observations**. RGB and NIR-HSI data were acquired for every observation.

## Dataset download

Download the dataset from the [ERDA published archive](https://erda.ku.dk/archives/f61461850198616c29294963a9b5540d/published-archive.html).

## Input and output

| Field or data type | Role | Description |
| --- | --- | --- |
| RGB kernel image | Input | Colour image of an individual barley kernel. |
| NIR-HSI kernel image | Optional input | Near-infrared hyperspectral image with 224 wavelength channels across 900–1700 nm. |
| Mean NIR spectrum | Optional input | Mean pseudo-absorbance spectrum calculated inside the kernel segmentation mask. |
| Segmentation mask | Supporting data | Mask identifying the kernel rather than the background. It may be used for preprocessing or segmentation work. |
| Germination label | Output | Expert label for the kernel at that imaging session: `germinated` or `not germinated`. |
| Kernel identity, Petri-dish identity, variety, and time point | Metadata | Information used to track observations across the six imaging sessions. Do not use identifiers as predictive inputs. |

The main task is **binary image classification**: predict whether a kernel is germinated or not germinated from an RGB image, NIR-HSI image, NIR spectrum, or an appropriate combination of these inputs.

## Using this dataset in assignments

This dataset can be used for **Assignment 2** and the **Final Project**. It is particularly appropriate for image-based or multimodal germination classification using a scientific model compatible with image or spectral inputs. It is not intended for Assignment 1, which is the traditional machine-learning case study.

Because the same kernel appears at multiple time points, students should split data by kernel or Petri dish rather than randomly splitting individual images. This avoids placing observations of the same kernel in both training and test data. Appropriate evaluation measures include accuracy, precision, recall, F1 score, Matthews correlation coefficient, and a confusion matrix.

## Reference

Engstrøm, O.-C. G., Dreier, E. S., Jespersen, B. M., & Pedersen, K. S. (2025). *A Time Series Dataset of NIR Spectra and RGB and NIR-HSI Images of the Barley Germination Process*. arXiv:2504.16658. https://arxiv.org/abs/2504.16658

The dataset is released under the CC BY-NC 4.0 licence.
