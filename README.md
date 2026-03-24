# Nut Shell Classifier

This project focuses on multi-class classification of shelled and unshelled nuts using a self-collected image dataset and a baseline Convolutional Neural Network (CNN) built with TensorFlow/Keras.

## Overview

The main goal of this project is to classify different nut types and shell conditions from images. The dataset was created manually by recording videos of nuts and extracting image frames with a separate Python-based dataset generator. The final dataset contains 13 classes and 28,594 images in total.

This repository should be viewed as an early computer vision project with two main contributions:

1. Building a custom dataset from self-recorded videos
2. Training a baseline CNN for multi-class classification

As an early computer vision project, it is best viewed as a custom dataset construction and baseline classification study rather than a benchmark-focused model.

## Classes

The dataset includes the following 13 classes:

- Almond_noShell
- Almond_withShell
- Hazelnut_noShell
- Hazelnut_withShell
- Peanut_noShell_noSkin
- Peanut_noShell_withSkin
- Peanut_withShell
- Pistachio_noShell
- Pistachio_withShell
- SunflowerSeed_noShell
- SunflowerSeed_withShell
- Walnut_noShell
- Walnut_withShell

## Dataset Construction

The dataset was created by:

- Recording original videos of different nut types and shell variants
- Extracting image frames from those videos using a separate dataset generator
- Organizing the images into 13 classes based on nut type and shell condition

The frame-extraction utility used for dataset generation is available here:

- [Video-To-Image-Dataset-Generator](https://github.com/giraydorukyurt7/Video-To-Image-Dataset-Generator)

This makes the project more meaningful as a custom dataset construction and baseline classification study rather than a benchmark-focused vision project.

## Dataset Split

| Class | Train | Validation | Test | Total |
|---|---:|---:|---:|---:|
| Almond_noShell | 1097 | 156 | 315 | 1568 |
| Almond_withShell | 1868 | 264 | 534 | 2666 |
| Hazelnut_noShell | 1199 | 175 | 343 | 1717 |
| Hazelnut_withShell | 728 | 103 | 208 | 1039 |
| Peanut_noShell_noSkin | 2421 | 347 | 691 | 3459 |
| Peanut_noShell_withSkin | 2047 | 293 | 587 | 2927 |
| Peanut_withShell | 2281 | 324 | 652 | 3257 |
| Pistachio_noShell | 2518 | 359 | 721 | 3598 |
| Pistachio_withShell | 2443 | 342 | 697 | 3482 |
| SunflowerSeed_noShell | 715 | 102 | 205 | 1022 |
| SunflowerSeed_withShell | 1025 | 149 | 293 | 1467 |
| Walnut_noShell | 785 | 116 | 225 | 1126 |
| Walnut_withShell | 887 | 125 | 254 | 1266 |
| **Overall** | **20014** | **2855** | **5725** | **28594** |

## Model

The classifier is a custom baseline CNN implemented with TensorFlow/Keras.

Architecture summary:

- 5 convolutional layers
- max pooling layers
- dense layers with dropout
- softmax output for 13-class classification

This project does not use transfer learning or fine-tuning. It is intended as a baseline CNN study.

## Baseline Results

- Test Accuracy: 80.6%
- Test Precision: 85.5%
- Test Recall: 76.1%
- Test Loss: 53.7%

## Important Note on Evaluation

Because the dataset was generated from frames extracted from recorded videos, nearby frames may still be visually similar. Although frames were sampled at intervals, the train/validation/test split was performed at the image level rather than the video/session level.

This means the reported metrics should be interpreted carefully, since frame-level splitting may introduce similarity between training and test samples. For that reason, this repository is best viewed as an early baseline project and a custom dataset construction effort rather than a final benchmark-quality evaluation.

## Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- OpenCV
- scikit-learn
- Matplotlib

## Future Improvements

Possible improvements for a more rigorous version of this project:

- video-level or session-level splitting
- stronger duplicate / near-duplicate control
- transfer learning with pretrained backbones
- better augmentation and regularization
- class-balanced evaluation and more robust validation design
