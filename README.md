# Gamified Sales Promotions and Consumer Decision-Making

Analysis code for a 2026 master's thesis by **Bui Ngoc Minh Quach** at the **Technical University of Munich**, M.Sc. Management & Digital Technology. The thesis was supervised by Sude Arslan at the Chair of Digital Marketing.

## Research question

Do gamified monetary rewards change consumers' excitement, urge to buy, and purchase intention? The main experiment compared three promotion designs.

| Condition | Promotion design |
| --- | --- |
| Non-gamified, certain | A guaranteed reward presented without a game |
| Gamified, certain | A guaranteed reward presented through a game |
| Gamified, chance-based | A chance-based reward presented through a game |

The analysis examines excitement as a mediator and impulse buying tendency as a moderator. A pretest assessed three candidate products and the proposed 15% discount for the main experiment.

## Notebooks

| Notebook | Workflow |
| --- | --- |
| [01 · Pretest](notebooks/01-pretest.ipynb) | Screens responses, constructs a product suitability index, compares product ratings using repeated-measures ANOVA, and evaluates the discount against the rating scale midpoint. |
| [02 · Main experiment](notebooks/02-main-experiment.ipynb) | Screens responses, constructs composite scores, assesses scale reliability and experimental manipulations, and runs ANOVA, planned contrasts, regression, mediation, moderated mediation, and robustness checks. |

The main notebook uses a fixed seed of 2026 and 10,000 bootstrap resamples per mediation or moderated mediation analysis.

## Reproduce the analysis with authorized data

From the repository root, create a Python 3.13 environment.

```bash
python3.13 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Place authorized copies of the original numeric-coded Qualtrics exports at the paths below. Keep the original headers, including whitespace, and the two Qualtrics label and import-information rows immediately below the headers. Each notebook reads its own file independently.

| Study | Local input | Generated workbook |
| --- | --- | --- |
| Pretest | `data/pretest/Pretest_Dataset.csv` | `outputs/pretest/tables/Pretest_Tables.xlsx` |
| Main experiment | `data/main/Final_Data.csv` | `outputs/main/Thesis_Tables.xlsx` |

Run `jupyter lab` from the repository root. Open each notebook with the Python 3 kernel from the virtual environment and select **Restart Kernel and Run All Cells**. The main notebook's bootstrap analyses may take several minutes. The notebooks also write derived participant-level CSVs below `outputs/`.

## Data availability

The survey exports and generated outputs are restricted. Both `data/` and `outputs/` are ignored by Git. The distributed notebooks have empty outputs and can be read on GitHub. Reproducing the empirical estimates requires authorized access to the original exports. Clear notebook outputs before committing any edits made after a private run.

## Citation

Quach, Bui Ngoc Minh. (2026). *The Effects of Gamified Monetary Reward Designs on Consumer Purchase Behavior: The Mediating Role of Excitement and the Moderating Role of Impulse Buying Tendency*. Master's thesis, Technical University of Munich.

The repository title is a short title for the analysis code. The citation uses the full title from the submitted notebooks.
