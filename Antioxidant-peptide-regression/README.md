# Antioxidant peptide regression dataset

## What is this dataset?

This dataset contains tripeptide sequences and their measured antioxidant activity in an ABTS radical-scavenging assay. Antioxidant activity is expressed as Trolox-equivalent antioxidant capacity (TEAC); higher values indicate greater antioxidant activity.

## Dataset file and size

`ABTS.xlsx` contains **130 tripeptide records**. The workbook has one worksheet:

- `ABTS`: the dataset for analysis.

All records are unique peptide sequences of length three. Nineteen records have an activity value of zero.

## Input and output

| Field | Role | Description |
| --- | --- | --- |
| `peptide_name` | Input | Tripeptide sequence, written using one-letter amino-acid codes. |
| `activity` | Output | Experimental ABTS antioxidant activity, expressed as TEAC in μmol Trolox equivalent (TE) per μmol peptide. Higher values indicate stronger antioxidant activity. |

This is principally a **sequence-to-property regression** dataset: predict `activity` from `peptide_name` (or features derived from the sequence).

## Using this dataset in assignments

This dataset can be used for **Assignment 1**, **Assignment 2**, and the **Final Project**. It supports either of the following task types:

- **Regression:** predict the numerical `activity` value from peptide sequence features or peptide representations.
- **Classification:** create activity labels by selecting and justifying a threshold. This requires an additional preprocessing step, because the original file does not contain a class-label column.

For a classification task, students should state how the activity threshold was chosen and how zero-activity peptides are treated.

Students should create training, validation, and test splits before model selection, or use cross-validation within the training data. For regression, appropriate measures include MAE, RMSE, and R²; for classification, report accuracy, precision, recall, F1 score, Matthews correlation coefficient, and a confusion matrix.

## Reference

Du, Z., Wang, D., & Li, Y. (2022). *Comprehensive Evaluation and Comparison of Machine Learning Methods in QSAR Modeling of Antioxidant Tripeptides*. **ACS Omega, 7**, 25760-25771. https://doi.org/10.1021/acsomega.2c03062
