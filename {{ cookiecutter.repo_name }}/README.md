{{cookiecutter.project_name}}
==============================

{{cookiecutter.description}}

The idea of the template is to automate the following steps:
- Download data to given folder
- Preprocess data to an easy-to-read format
- Explore data in `exploration`
- Run one-off tests in `notebooks` (rename as `analysis`?)

To reproduce, `make [all]` should consist of following (or similar):
- `make download`
- `make preprocess`
- `make train model=resnet-thingy`
- `make submission`

Project Organization
------------

```
    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    |
    |── input              <- Raw data downloaded from Kaggle with `make download`
    |
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── kernels            <- Jupyter notebooks. Naming convention is a number (for ordering),
    │   ├── exploration       the creator's initials, and a short `-` delimited description, e.g.
    │   ├── preprocessing     `1.0-jqp-initial-data-exploration`.
    │   └── submissions
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    └── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
                              generated with `pip freeze > requirements.txt`

```