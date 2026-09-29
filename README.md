# BSEN41030 Assignment Resources

This repository contains 13 scientific and engineering datasets, assignment notebook templates, and an Umami worked example for BSEN41030 coursework. Follow the module's official guidance for assessment and submission requirements.

Choose a dataset from the table below and read the `README.md` inside its folder before using the data. Each folder provides the dataset-specific description, files, reference, and instructions.

## Assignment templates

The [Assignment-template](Assignment-template/) folder provides Jupyter notebooks (`.ipynb`) to structure your work:

| Resource | Purpose |
| --- | --- |
| [Assignment 1 template](Assignment-template/Assignment-1-template.ipynb) | **Traditional Machine Learning Case Study**: develop a classification or regression workflow using a traditional ML method, such as a random forest or SVM. |
| [Assignment 2 template](Assignment-template/Assignment-2-template.ipynb) | **Scientific LLM-Based Case Study**: use a sequence-based dataset with a scientific language model, through pre-trained embeddings and a downstream predictor or model fine-tuning. |
| [Umami Assignment 1 example](Assignment-template/Umami-assignments-demo/Assignment-1-umami.ipynb) | Illustrates the Assignment 1 workflow using amino-acid composition features and a random forest for umami peptide classification. The accompanying train/test files are in the example's [data folder](Assignment-template/Umami-assignments-demo/data/). |

Both templates follow the same structure: setup, data import, preprocessing, train/test split, model selection, hyperparameter optimisation, evaluation, and AI acknowledgement.

### Using a template

1. Download the appropriate notebook and open your own copy in Jupyter Notebook, JupyterLab, or Google Colab.
2. Fill in your name and dataset (and the pre-trained model for Assignment 2). Read the selected dataset's README and update data paths for your environment.
3. Complete Sections 1–6 in order with your code and explanations, then complete Section 7 (AI acknowledgement).
4. Use a fixed random seed and preserve any provided train/test split. Fit data-dependent preprocessing and tune models using only the training data; reserve the held-out test set for final evaluation.
5. Before submitting, **Restart & Run All** and save the notebook **with its outputs**.

For the Umami example, download the whole `Umami-assignments-demo` folder and keep its `data/` subfolder alongside the notebook so the relative data paths work. Use the example as a guide when developing your own analysis.

For Assignment 2, a GPU is recommended for larger models or fine-tuning. In Google Colab, select **Runtime → Change runtime type → T4 GPU**.

## Datasets

| Folder | Dataset topic | Typical task |
| --- | --- | --- |
| [Antihypertensive-peptide-regression](Antihypertensive-peptide-regression/) | ACE-inhibitory food peptides | Regression or classification |
| [Antimicrobial-peptide-regression](Antimicrobial-peptide-regression/) | Antimicrobial peptide activity against *E. coli* | Regression or classification |
| [Antioxidant-molecules-regression](Antioxidant-molecules-regression/) | Antioxidant activity of small molecules | Regression or classification |
| [Antioxidant-peptide-regression](Antioxidant-peptide-regression/) | Antioxidant activity of tripeptides | Regression or classification |
| [Barley-germination-image-classification](Barley-germination-image-classification/) | RGB and hyperspectral images of germinating barley | Image classification |
| [Cell-penerating-peptides-classification](Cell-penerating-peptides-classification/) | Cell-penetrating peptide sequences | Binary classification |
| [E.coli-protein-solubility-regression](E.coli-protein-solubility-regression/) | *E. coli* protein solubility | Regression or classification |
| [Fruits-Classification](Fruits-Classification/) | Images of five fruit types | Multi-class image classification |
| [Fruits-fresheness-Classification](Fruits-fresheness-Classification/) | Fresh and rotten fruit images | Binary or multi-class image classification |
| [HSI-fruit-ripeness-classification](HSI-fruit-ripeness-classification/) | Hyperspectral fruit-ripeness data | Multi-class classification |
| [Molecular-taste-classification](Molecular-taste-classification/) | Taste classes of small molecules | Multi-class classification |
| [NIR-soil-properties-regression](NIR-soil-properties-regression/) | NIR spectra and soil properties | Regression |
| [Umami-peptide-classification](Umami-peptide-classification/) | Umami and non-umami peptide sequences | Binary classification |

## How to use this repository

- Start with the relevant [assignment template](Assignment-template/) and select a dataset appropriate for the assessment and method you plan to use.
- Read its folder README before downloading, preprocessing, or modelling.
- Some datasets are too large to store here; their folder README provides the original download link.

You are responsible for understanding the data, using an appropriate evaluation strategy, and acknowledging any generative-AI or AI-assisted coding tools used in your work.
