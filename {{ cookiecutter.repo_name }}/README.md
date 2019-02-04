# {{cookiecutter.project_name}}

{{cookiecutter.description}}

## Instructions

Download Kaggle data to `input` and unzip:

```bash
$ make download
```

Preprocess data:
```bash
$ make preprocess [kernel=preprocess.ipynb]
```

Run the winning submission:
```bash
$ make train [kernel=train.ipynb]
```

For reproducibility, `make all` should perform all these steps in a pipeline.

**Important**

Kaggle kernels expect to find the dataset in directory `../input`. In contrast, for a notebook in path
`kernels/exploration`, the dataset is found in `../../input`. To be able to use the same code
both locally and in Kaggle, add a symbolic link in `kernels/` pointing to `input/`:

```bash
ln -sf ../input ./kernels/input
```

## Notebook organization

- Explore data using notebooks in `kernels/exploration`
- Experiment on preprocessing in `kernels/preprocessing`
- Run one-off tests in `kernels/submissions`

To reproduce, `make [all]` does the following:
- `make download`
- `make preprocess`
- `make train model=resnet-thingy`

Project created with the [cookiecutter](https://github.com/audreyr/cookiecutter)
template for [Kaggle competitions](https://github.com/Meeshkan/cookiecutter-kaggle-kernels).

#### Detailed organization

```
    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make download` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── unzip_input.sh     <- Bash script for unzipping all archives in `input`
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
    │   ├── train
    │   └── submissions
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    └── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
                              generated with `pip freeze > requirements.txt`

```