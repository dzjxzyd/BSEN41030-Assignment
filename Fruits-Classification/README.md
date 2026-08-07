# Fruit image classification dataset

## What is this dataset?

This dataset contains labelled images of five fruit types: Apple, Banana, Grape, Mango, and Strawberry. It is intended for supervised image classification: a model receives a fruit image and predicts its fruit class.

## Dataset files and size

The dataset contains **10,000 images** in total, with **2,000 images per class**. Images are provided in JPEG and PNG formats and have varying pixel dimensions. The supplied folders define the data splits:

| Folder | Images per class | Total images | Purpose |
| --- | ---: | ---: | --- |
| `train/` | 1,940 | 9,700 | Model training |
| `valid/` | 40 | 200 | Validation during model development |
| `test/` | 20 | 100 | Final model evaluation |

The class label for an image is given by the name of its immediate parent folder (for example, `train/Apple/` contains images labelled `Apple`).

## Input and output

| Item | Role | Description |
| --- | --- | --- |
| Image file | Input | A colour fruit image in JPEG or PNG format. Images should be resized and converted to the numerical representation required by the chosen model. |
| Folder name | Output | One of five class labels: `Apple`, `Banana`, `Grape`, `Mango`, or `Strawberry`. |

This is a **five-class image-classification** dataset. The provided `train`, `valid`, and `test` folders should be retained as separate splits when evaluating a model.

## Using this dataset in assignments

This dataset can be used for **Assignment 2: Scientific LLM-Based Case Study** and the **Final Project**. For Assignment 2, students can apply an appropriate image-based scientific foundation model or image representation method, then train and evaluate a classifier for the five fruit classes. It is not intended for Assignment 1, which focuses on traditional machine-learning methods.

The provided training, validation, and test folders should be retained as separate splits. Students should not use the test set for model selection. Appropriate evaluation measures include accuracy, precision, recall, F1 score, Matthews correlation coefficient, and a confusion matrix.

## Reference

This dataset was downloaded from the Kaggle dataset *Fruits Classification* by utkarshsaxenadn:

https://www.kaggle.com/datasets/utkarshsaxenadn/fruits-classification
