# *E. coli* protein solubility regression dataset

## What is this dataset?

This eSOL dataset contains *Escherichia coli* protein sequences and experimentally measured solubility values. The proteins were produced using a PURE cell-free expression system. Solubility is defined as the ratio of protein in the supernatant fraction to the total protein fraction; values range from 0 to 1, where higher values indicate greater solubility.

## Dataset files and size

The supplied dataset contains **2,679 protein sequences** in a predefined training and test split:

- `eSol_train.fasta`: **2,019** training sequences.
- `eSol_test.fasta`: **660** independent test sequences.

Each FASTA record has a header in the form `>protein_identifier_solubility`, followed by the amino-acid sequence. For example, `>acpS_0.84` identifies the protein as `acpS` and gives its solubility value as `0.84`.

## Input and output

| Field | Role | Description |
| --- | --- | --- |
| Amino-acid sequence | Input | Protein sequence written using one-letter amino-acid codes. |
| Solubility value | Output | Continuous experimental solubility value between 0 and 1, stored as the final value in the FASTA header. Higher values indicate greater solubility. |
| Protein identifier | Metadata | Identifier stored in the first part of the FASTA header. Do not use this as a model input. |

This is principally a **sequence-to-property regression** dataset: predict protein solubility from the amino-acid sequence or sequence-derived features.

## Using this dataset in assignments

This dataset can be used for **Assignment 1**, **Assignment 2**, and the **Final Project**. It can support either of the following task types:

- **Regression:** predict the continuous solubility value from protein sequence features or protein representations.
- **Classification:** create soluble and insoluble labels by selecting and justifying a threshold. This requires an additional preprocessing step, because the original files do not contain a class-label field.

For example, the accompanying reference paper uses a threshold of `0.5`: proteins with solubility values `≥ 0.5` are treated as soluble and those with values below `0.5` as insoluble. Students choosing a classification task should state and justify their labelling rule.

The provided training and test files should be retained as separate splits. Students may use a further validation split or cross-validation within the training data, but should not use the independent test set for model selection. For regression, appropriate measures include MAE, RMSE, and R²; for classification, report accuracy, precision, recall, F1 score, Matthews correlation coefficient, and a confusion matrix.

## Reference

Niwa, T., Ying, B.-W., Saito, K., Jin, W., Takada, S., Ueda, T., & Taguchi, H. (2009). *Bimodal protein solubility distribution revealed by an aggregation analysis of the entire ensemble of Escherichia coli proteins*. **Proceedings of the National Academy of Sciences, 106**(11), 4201–4206. https://doi.org/10.1073/pnas.0811922106

The supplied benchmark split and its use for regression are described in Deng, W., Chen, Z., Ji, C., Gao, J., Xu, H., & Huang, J. (2026). *ProtSATT: An Advanced Protein Solubility Predictor Based on Attention Mechanism*. **Journal of Chemical Information and Modeling, 66**, 6334–6349. https://doi.org/10.1021/acs.jcim.6c00821.
