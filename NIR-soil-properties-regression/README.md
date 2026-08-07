# NIR soil-properties regression dataset

## What is this dataset?

This dataset contains near-infrared (NIR) spectra from **190 agricultural soil samples** collected in northern Thailand. It supports prediction of soil organic matter and total carbon from soil spectra acquired with a homemade NIR spectrometer.

The labelled modelling dataset is provided in `Data research.xlsx`. Each sample has a mean spectrum spanning **228 wavelengths** from approximately **901 to 1,701 nm**, together with the measured soil-property targets `OM (%)` and `TC (%)`.

## Dataset files and size

| File or folder | Contents |
| --- | --- |
| `Data research.xlsx` | Labelled dataset. It contains the raw mean spectrum with chemical targets, plus raw and six preprocessed spectral versions: smoothing, MSC, SNV, first derivative, second derivative, and mean centering. |

This is the only data file provided in this folder. The original source publication also includes repeat NIR scans (`Homemade NIR Spectral.xlsx`), pretrained model files (`*-SOM-Model.41M`, `*-TC-Model.41M`), and a `Result/` folder of calibration/validation predictions on Mendeley Data (see Reference below), but these are not distributed here.

## Input and output

| Field | Role | Description |
| --- | --- | --- |
| `Sample number` | Identifier | Sample identifier. Do not use it as a predictive input. |
| Wavelength columns (about 901–1,701 nm) | Input | NIR spectral measurements used as regression features. |
| `OM (%)` | Output | Soil organic-matter percentage. |
| `TC (%)` | Output | Total-carbon percentage. |

This is a **spectra-to-property regression** dataset. The two targets may be modelled separately. The source study uses a 70% calibration and 30% validation split; retain a fixed held-out test set when creating a new evaluation protocol.

## Using this dataset in assignments

This dataset can be used for **Assignment 1**, **Assignment 2**, and the **Final Project**.

- **Regression:** predict `OM (%)` or `TC (%)` using raw or preprocessed NIR spectra.
- **Preprocessing study:** compare raw spectra with smoothing, MSC, SNV, derivative, or mean-centred representations.
- **Evaluation:** report MAE, RMSE, R², and an observed-versus-predicted plot. Do not use `Sample number` as a feature.

## Reference

Santasup, N., Theanjumpol, P., Santasup, C., Kittiwachana, S., Mawan, N., & Khongdee, N. (2025). *Dataset of near-infrared (NIR) spectral data for prediction of organic matter and total carbon in agricultural soil using homemade NIR spectrometer*. **Data in Brief, 61**, 111840. https://doi.org/10.1016/j.dib.2025.111840

The source dataset is available from [Mendeley Data](https://data.mendeley.com/datasets/yt78nwnhbd/2).
