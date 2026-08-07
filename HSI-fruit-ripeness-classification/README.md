# Hyperspectral fruit-ripeness classification dataset

## What is this dataset?

DeepHS-Fruit is a hyperspectral-imaging dataset for the non-destructive assessment of fruit ripeness. A hyperspectral image is an image cube: every pixel has a spectrum measured over many wavelengths, rather than just the three red, green and blue channels of an ordinary colour image. This can capture information related to chemical and structural changes during ripening that may not be visible in RGB images.

The original study introduced a three-class prediction problem for fruit ripeness: **unripe**, **ripe/perfect**, and **overripe**. It used destructive reference measurements, including fruit-flesh firmness, sugar content, and an overall ripeness assessment, as labels.

The current DeepHS-Fruit release contains recordings of:

- avocado;
- kiwi;
- kaki (persimmon);
- mango; and
- papaya.

It was acquired with three hyperspectral cameras: Specim FX 10, INNO-SPEC Redeye 1.7, and Corning microHSI 410 Vis-NIR. The original 2021 paper focuses on avocado and kiwi recordings. The later public release expands the collection with additional fruits and measurement series.

## Download the data from the original source

The full dataset is deliberately **not distributed with this teaching repository** because it is very large. Do not treat any files that happen to be present in this folder as a complete dataset or as an official train/validation/test split.

Download the fruit archive(s) and the annotation archive from one of the following official sources:

- [DeepHS-Fruit GitHub repository](https://github.com/cogsys-tuebingen/deephs_fruit) - official code, documentation, and example training commands.
- [DeepHS-Fruit 2023 dataset download page](https://cogsys.cs.uni-tuebingen.de/webprojects/DeepHS-Fruit-2023-Datasets/) - fruit archives, annotations, and a torrent file. Archives range from approximately 2 GB to 72 GB, so download only the fruit(s) needed for your project.

Read the upstream documentation and licence terms before downloading or using the data. Keep the downloaded data outside this course repository unless you have sufficient storage and a clear reason to do otherwise.

## Data format

The hyperspectral recordings are supplied in ENVI format:

| File | Purpose |
| --- | --- |
| `.hdr` | Text header describing the image dimensions, number of spectral bands, numerical data type, byte order, and interleave format. |
| `.bin` | Binary hyperspectral image data corresponding to the header file. |
| Annotation files | Labels and measurement metadata supplied separately by the dataset authors. Use the current annotation archive from the official download page. |

For example, recordings from the Specim FX 10 camera have 224 spectral channels covering approximately 400-1000 nm. Read each `.hdr` file rather than assuming that every recording has the same dimensions, wavelengths, or camera settings.

Each recording normally represents one fruit, with front and back views. The source data also contain repeated measurements across days. These relationships are important when creating data splits.

## Input and output

| Item | Role | Description |
| --- | --- | --- |
| Hyperspectral image cube | Input | Spatial image data with a spectrum at each pixel. Students may use the full cube, selected spectral bands, spectral summaries, or a representation learned by a suitable model. |
| Fruit type and acquisition metadata | Metadata | Fruit, camera, measurement series, day, view, and identifier information. Use these to understand the data and make leakage-safe splits; do not use arbitrary identifiers as predictive features. |
| Firmness measurement | Possible output | Destructive penetrometer measurement. The paper converts this into three firmness classes. |
| Sugar content | Possible output | Soluble-solids/sugar measurement (for applicable fruits). The paper uses three sweetness classes for kiwi. |
| Overall ripeness label | Possible output | Three classes: unripe, ripe/perfect, and overripe, based on the source assessment. |

This dataset can therefore support **multi-class classification** of ripeness or firmness/sweetness categories. A regression task using the continuous destructive measurements may also be possible if the relevant labels are available and the task definition is clearly justified.

## Using this dataset in assignments

This dataset is suitable for **Assignment 2: Scientific LLM-Based Case Study** and the **Final Project**. It is particularly appropriate for a scientific vision, hyperspectral, or multimodal foundation-model approach. It is not intended for Assignment 1, which is the traditional machine-learning case study.

Possible project directions include:

- classify overall ripeness for one fruit type;
- compare full hyperspectral input with an RGB approximation or selected bands;
- predict firmness or sweetness categories where the annotations support this;
- compare a simple baseline with a hyperspectral deep-learning or foundation-model representation; or
- examine transfer across fruit types or cameras, provided that the split and limitations are carefully justified.

Students must define one precise prediction target, identify the exact annotations used, and report the number of usable recordings after preprocessing. Do not combine labels from different fruit types, cameras, or measurement series without checking that their meanings and acquisition conditions are comparable.

### Avoid data leakage

Do **not** randomly split individual views or individual day-level recordings. The front/back views of the same fruit, and repeated measurements of the same fruit across days, must remain in the same partition. Where possible, split by fruit identity; a more conservative option is to split by measurement series or acquisition batch. Explain and justify the selected strategy in the report.

Keep a held-out test set for final evaluation only. Use a validation set, or cross-validation within the training data, for model selection and tuning.

### Evaluation

For a three-class classification task, report:

- class counts for every data split;
- accuracy and macro-averaged precision, recall, and F1 score;
- a confusion matrix; and
- per-class results, especially if the classes are imbalanced.

If you formulate a regression task, report MAE, RMSE, R-squared, and an observed-versus-predicted plot. In all cases, compare against a simple, appropriate baseline and critically discuss small sample size, destructive/partial labels, camera differences, and limits on generalisation.

## Reference

Varga, L. A., Makowski, J., & Zell, A. (2021). *Measuring the Ripeness of Fruit with Hyperspectral Imaging and Deep Learning*. Proceedings of the 2021 International Joint Conference on Neural Networks (IJCNN), 1-8. https://doi.org/10.1109/IJCNN52387.2021.9533728

Cite both this paper and the DeepHS-Fruit dataset/repository in your work where appropriate.
