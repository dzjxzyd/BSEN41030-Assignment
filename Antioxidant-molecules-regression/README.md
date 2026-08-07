# Antioxidant molecule regression dataset

## What is this dataset?

This dataset contains small molecules tested for antioxidant activity using the 1,1-diphenyl-2-picrylhydrazyl (DPPH) radical-scavenging assay with a 30-minute assay time. Antioxidant activity is represented by the half-maximal inhibitory concentration (IC50). The target is stored as `−LogIC50 (M)` (pIC50), the negative base-10 logarithm of IC50 expressed in molar units. Higher pIC50 values indicate lower IC50 values and therefore stronger antioxidant activity.

## Dataset files and size

`DPPH_30min_Dataset.xlsx` contains the complete curated dataset of **1,911 small molecules**. The same records are provided as fixed analysis splits:

- `train.csv`: **1,528** molecules.
- `val.csv`: **191** molecules.
- `test.csv`: **192** molecules.

`split-dataset.ipynb` is an example notebook that uses these fixed splits for molecular-representation regression experiments.

## Input and output

| Field | Role | Description |
| --- | --- | --- |
| `Canonical SMILES` | Input | Canonical SMILES representation of the molecular structure. |
| `−LogIC50 (M)` | Output | pIC50: `−log10(IC50 in M)` measured in the DPPH radical-scavenging assay after 30 minutes. Higher values indicate stronger antioxidant activity. |
| `inChI`, `Molecular Weight`, `ChEMBL ID`, `DOI`, `Assay Description`, `row ID` | Metadata | Molecular identifiers, molecular weight, source and assay information. Do not use source identifiers such as `row ID`, `ChEMBL ID`, or `DOI` as model inputs. |

This is a **molecule-to-property regression** dataset: predict `−LogIC50 (M)` from molecular structure or representations derived from the SMILES string.

## Using this dataset in assignments

This dataset can be used for **Assignment 1**, **Assignment 2**, and the **Final Project**.

- **Regression:** predict the numerical `−LogIC50 (M)` value using molecular descriptors, fingerprints, or molecular-language-model representations.
- **Classification:** students may create activity labels by selecting and justifying a pIC50 or IC50 threshold. This requires an additional preprocessing step because the original dataset does not contain a class-label column.

The provided training, validation, and test files should be retained as separate splits. Students should not use the test set for model selection. For regression, appropriate measures include MAE, RMSE, and R²; for classification, report accuracy, precision, recall, F1 score, Matthews correlation coefficient, and a confusion matrix.

## Reference

Ghironi, S., Viganò, E. L., Selvestrel, G., & Benfenati, E. (2025). *QSAR Models for Predicting the Antioxidant Potential of Chemical Substances*. **Journal of Xenobiotics, 15**(3), 80. https://doi.org/10.3390/jox15030080
