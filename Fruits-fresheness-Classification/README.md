# Fruit freshness image classification dataset

## What is this dataset?

This dataset contains photographs of strawberries, peaches, and pomegranates labelled as fresh or rotten. It can be used to develop image-classification models for fruit freshness assessment, with potential applications in food quality control and post-harvest monitoring.

## Dataset files and size

The dataset is organised into six folders. Folder names provide the labels:

| Folder | Class | Images |
| --- | --- | ---: |
| `fresh_peaches_done` | Fresh peach | 250 |
| `fresh_pomegranates_done` | Fresh pomegranate | 311 |
| `fresh_strawberries_done` | Fresh strawberry | 250 |
| `rotten_peaches_done` | Rotten peach | 343 |
| `rotten_pomegranates_done` | Rotten pomegranate | 250 |
| `rotten_strawberries_done` | Rotten strawberry | 251 |

The supplied folders contain **1,655 RGB JPEG images**, each with a resolution of **300 × 300 pixels**. There are **811 fresh** and **844 rotten** fruit images.

## Input and output

| Item | Role | Description |
| --- | --- | --- |
| Image | Input | An RGB JPEG image of a strawberry, peach, or pomegranate (300 × 300 pixels). |
| Folder name | Output label | The folder identifies both the fruit type and freshness condition. |

This dataset supports several image-classification formulations. It can be treated as a six-class task (fresh/rotten × fruit type) or as a binary fresh-versus-rotten task. Students must state and justify the task definition they use.

## Using this dataset in assignments

This dataset can be used for **Assignment 2** and the **Final Project**, particularly for image-classification approaches using vision or vision-language models covered in the module. It is **not intended for Assignment 1**, which is a traditional machine-learning case study.

Students should create their own training, validation, and test splits and evaluate performance using appropriate classification metrics, such as accuracy, precision, recall, F1 score, and a confusion matrix.

## Reference

GTS. (2025). *Fruits Dataset for Classification* (Version 1). **Mendeley Data**. https://doi.org/10.17632/rg254yr63x.1
