# Antihypertensive peptide regression dataset

## What is this dataset?

This dataset contains food-derived peptide sequences and their reported ability to inhibit angiotensin-converting enzyme I (ACE-I). ACE-I inhibition is used as an indicator of potential antihypertensive activity. A lower IC50 indicates that less peptide is required to inhibit 50% of ACE-I activity and therefore indicates stronger inhibitory activity.

## Dataset file and size

`final_data_set_with reference_delete_duplication——1386.xlsx` contains **1,386 peptide records** (excluding the blank final row). The workbook has two sheets:

- `Sheet1`: the dataset for analysis.
- `reference list no duplciation`: a de-duplicated list of the literature sources used in the dataset.

## Input and output

| Field | Role | Description |
| --- | --- | --- |
| `sequence` | Input | Peptide sequence, written using one-letter amino-acid codes. |
| `IC50` | Output | Experimental ACE-I half-maximal inhibitory concentration, in μM. Lower values indicate stronger ACE-I inhibition. `No activity` denotes no reported ACE-I inhibitory activity. |
| `reference` | Metadata | Literature source for the reported peptide and activity value. Do not use this as a model input. |

This is principally a **sequence-to-property regression** dataset: predict `IC50` from `sequence` (or features derived from the sequence). Before modelling, decide and document how you treat rows labelled `No activity`; they are not numeric IC50 measurements.

## Using this dataset in assignments

This dataset can be used for **Assignment 1**, **Assignment 2**, and the **Final Project**. It supports either of the following task types:

- **Regression:** predict the numerical `IC50` value from peptide sequence features or peptide representations.
- **Classification:** create activity labels from `IC50` by selecting and justifying a threshold. This requires an additional preprocessing step, because the original file does not contain a class-label column.

For example, the accompanying reference paper treats peptides with `IC50 ≤ 100 μM` as ACE-I inhibitory (positive) and peptides with `IC50 > 1000 μM` as non-functional (negative); values between these thresholds are described as average activity. Students choosing a binary classification task must state how they handle the intermediate values and `No activity` records, and justify their chosen labelling rule.

Students should create training, validation, and test splits before model selection, or use cross-validation within the training data. For regression, appropriate measures include MAE, RMSE, and R²; for classification, report accuracy, precision, recall, F1 score, Matthews correlation coefficient, and a confusion matrix.

## Reference

Hazra, S., Nandhini, S., S. K., Mukherjee, A., & Nandi, S. (2021). *Anti-hypertensive Peptide Predictor: A Machine Learning-Empowered Web Server for Prediction of Food-Derived Peptides with Potential Angiotensin-Converting Enzyme-I Inhibitory Activity*. **Journal of Agricultural and Food Chemistry, 69**(49), 14995–15004. https://doi.org/10.1021/acs.jafc.1c04555
