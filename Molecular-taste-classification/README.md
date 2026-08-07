# Molecular taste classification dataset

## What is this dataset?

This dataset contains small molecules and their reported taste categories. Each molecule is represented by a canonicalized SMILES string, a text-based notation for chemical structure. The dataset was compiled for molecular taste prediction and contains five classes: `sweet`, `bitter`, `sour`, `umami`, and `undefined`.

The `undefined` class groups molecules that cannot be assigned to the four specified taste categories; this includes salty, tasteless, and ambiguous taste profiles. Salty taste was not treated as a separate structure-based class in the reference study.

## Dataset files and size

The supplied dataset contains **15,025 records** in predefined training, validation, and test splits:

- `fart_train.csv`: **10,517** labelled records.
- `fart_val.csv`: **2,254** labelled records.
- `fart_test.csv`: **2,254** labelled records.

The five taste classes are imbalanced. Across all supplied files, there are 9,584 `sweet`, 2,077 `undefined`, 1,695 `bitter`, 1,607 `sour`, and 62 `umami` records. Some molecules occur more than once when they have multiple reported taste labels; the `is_multiclass` field identifies these records.

## Input and output

| Field | Role | Description |
| --- | --- | --- |
| `Canonicalized SMILES` | Input | Canonicalized SMILES representation of the molecular structure. |
| `Canonicalized Taste` | Output | Molecular taste class: `sweet`, `bitter`, `sour`, `umami`, or `undefined`. |
| `Standardized SMILES` | Optional input | Standardized SMILES representation of the molecular structure. Students should select one SMILES representation and use it consistently. |
| `Original Labels` | Metadata | Original taste annotation(s) from the source dataset. Do not use this as a model input. |
| `Source` | Metadata | Source database or literature source. Do not use this as a model input. |
| `is_multiclass` | Metadata | `1` indicates a record associated with a molecule that has multiple reported taste labels; `0` otherwise. Do not use this as a model input. |
| Unnamed first column | Identifier | Record identifier. Do not use this as a model input. |

This is a **multi-class molecular classification** dataset: predict the taste class from the SMILES string or features derived from molecular structure.

## Using this dataset in assignments

This dataset can be used for **Assignment 1**, **Assignment 2**, and the **Final Project**.

- **Multi-class classification:** predict one of the five taste classes from molecular descriptors, fingerprints, molecular graphs, or SMILES representations.
- **Binary classification:** create and justify a one-versus-rest task, for example `sweet` versus non-`sweet`. This requires a clear labelling rule and careful consideration of the substantial class imbalance.

The provided training, validation, and test files should be retained as separate splits. The test file includes labels for final independent evaluation, but should not be used for model selection. Appropriate evaluation measures include accuracy, macro-averaged precision, recall and F1 score, Matthews correlation coefficient, and a confusion matrix. Macro-averaged measures are particularly important because `umami` is rare.

## Reference

Zimmermann, Y., Sieben, L., Seng, H., Pestlin, P., & Görlich, F. (2025). *A chemical language model for molecular taste prediction*. **npj Science of Food, 9**, 122. https://doi.org/10.1038/s41538-025-00474-z
