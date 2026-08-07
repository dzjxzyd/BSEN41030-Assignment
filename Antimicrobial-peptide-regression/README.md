# Antimicrobial peptide regression dataset

## What is this dataset?

This dataset contains peptide sequences with experimentally measured antimicrobial activity against *Escherichia coli* (*E. coli*), represented by the minimum inhibitory concentration (MIC). MIC is the lowest concentration that prevents visible microbial growth. Lower MIC values indicate stronger antimicrobial activity. In this supplied dataset, the MIC target has been log-transformed.

## Dataset file and size

`mic_data.csv` contains **4,546 unique peptide sequences**. The source study selected measurements against *E. coli* and averaged multiple MIC measurements for the same peptide. Sequence lengths in the supplied file range from 2 to 190 amino acids.

## Input and output

| Field | Role | Description |
| --- | --- | --- |
| Unnamed first column | Identifier | Row index only. It can be ignored for modelling. |
| `sequence` | Input | Peptide sequence, written using one-letter amino-acid codes. |
| `value` | Output | `log10(MIC)` activity value, where MIC is in μg/mL. For example, `value = 1.5` corresponds to an MIC of `10^1.5` ≈ 32 μg/mL. Lower values correspond to lower MIC and hence stronger antimicrobial activity. |

This is a **sequence-to-property regression** dataset: predict `value` from `sequence` (or features derived from the sequence). The supplied file contains `log10(MIC)` rather than raw MIC values. Students should interpret predictions on this transformed scale, or explicitly apply the inverse transformation (`MIC = 10^value`) when reporting MIC in μg/mL.

## Using this dataset in assignments

This dataset can be used for **Assignment 1**, **Assignment 2**, and the **Final Project**. It supports either of the following task types:

- **Regression:** predict the MIC-derived `value` from peptide sequence features or peptide representations.
- **Classification:** create a high-activity/low-activity label by selecting and justifying a threshold on `value`. This requires an additional preprocessing step, because the CSV does not contain a class-label column.

The accompanying reference paper uses an MIC threshold of approximately 32 μg/mL (`10^1.5`) to distinguish active from inactive peptides. On the supplied log-transformed scale, this is `value ≤ 1.5` for active peptides and `value > 1.5` for inactive peptides. Students should document any alternative threshold they use.

Students should create training, validation, and test splits before model selection, or use cross-validation within the training data. For regression, appropriate measures include MAE, RMSE, and R²; for classification, report accuracy, precision, recall, F1 score, Matthews correlation coefficient, and a confusion matrix.

## Reference

Szymczak, P., Możejko, M., Grzegorzek, T., *et al.* (2023). *Discovering highly potent antimicrobial peptides with deep generative model HydrAMP*. **Nature Communications, 14**, 1453. https://doi.org/10.1038/s41467-023-36994-z
