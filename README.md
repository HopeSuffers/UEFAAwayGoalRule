# UEFA's Away Goals Rule
## Champions League Analysis

This repository contains an exploratory data analysis of the UEFA Champions League with a focus on the impact of the (now abolished) **away goals rule** in two legged knockout ties.

The project is built around Jupyter notebooks and uses publicly available match data from the excellent [`champions_uefa_data`](https://github.com/CharlieGnomo/champions_uefa_data) dataset.

---

## Background

From 1965 until the start of the **2021/22** season, UEFA club competitions used the away goals rule to decide two legged ties that finished level on aggregate: the team with more goals scored away from home progressed.

In June 2021, UEFA decided to abolish the away goals rule across all club competitions, starting from the 2021/22 season. Ties that are level on aggregate are now decided by extra time and, if necessary, penalties rather than away goals.  

This project uses historical Champions League data to explore questions such as:

- How often did ties actually get decided by away goals?
- How did the rule affect the balance between home and away performance?
- What would have changed in selected ties if away goals had *not* been used?

> Note: The exact questions and visualisations are implemented in the notebooks inside this repository. This README describes how to run them and the general analytical intent.

---

## Data

All raw data comes from the public repository:  
**[`CharlieGnomo/champions_uefa_data`](https://github.com/CharlieGnomo/champions_uefa_data)**

That dataset provides CSV files with match level and competition level information for the European Cup / UEFA Champions League, covering seasons from **1955–56 to 2021–22** (inclusive). It includes, among others:

- `matches.csv` – fixtures and results
- `goals.csv` – goal level data
- `teams.csv` – team metadata
- `players.csv` – player metadata
- `stadiums.csv` – stadium metadata
- `referees.csv` – referee metadata
- `winners.csv` – competition winners by season
- `uefa_agg_points.csv`, `uefa_season_points.csv`, `uefa_fed_points.csv` – coefficients / points
- `weather.csv` – weather information for matches

In this project, those CSVs are used to reconstruct two legged knockout ties and study home vs. away performance under the away goals regime.

**Licensing note:** The underlying data is licensed under the Apache-2.0 license in the original repository. Please refer to `CharlieGnomo/champions_uefa_data` for the data’s license and terms of use.

---

## Repository structure

At a high level this repository is organised as:

- `notebooks/`  
  Jupyter notebooks containing the analysis of the Champions League data and the away goals rule (data loading, feature engineering, visualisation, etc.).

- `data/`  
  Local copies or links to the CSV files from `champions_uefa_data`.

- `pyproject.toml`  
  Project and dependency configuration for the Python environment.

- `uv.lock`  
  Lockfile for the [`uv`](https://docs.astral.sh/uv/) Python package & project manager, ensuring reproducible environments.

- `.gitignore`  
  Standard Git ignore rules (e.g. for virtual environments, notebook checkpoints, etc.).

---

## Prerequisites

You will need:

- A recent **Python 3** installation (e.g. 3.10+).
- **Git** to clone the repository.
- A way to run **Jupyter notebooks**.

Dependencies for the analysis itself (pandas, plotting libraries, etc.) are declared in `pyproject.toml`. This repository is set up to be managed with **uv**, but you can also use plain `pip` or `conda` if you prefer.

---

## Getting started

### Clone this repository

```bash
git clone https://github.com/HopeSuffers/UEFAAwayGoalRule.git
cd UEFAAwayGoalRule
```
---

## Python environment

This repository already includes a `pyproject.toml` and `uv.lock`, so you can use [`uv`](https://docs.astral.sh/uv/) to create a reproducible environment.

1. **Install `uv`**  
   Follow the official installation instructions for your platform from the uv docs.

2. **Sync the project environment**

   From the project root:

   ```bash
   uv sync
   ```

   This will create a local `.venv` and install all dependencies declared in `pyproject.toml` using the versions pinned in `uv.lock`.

3. **Run Jupyter within the environment**

   ```bash
   uv run jupyter lab
   # or
   uv run jupyter notebook
   ```

   `uv run` ensures Jupyter is executed inside the project’s virtual environment.

---

## Acknowledgements

- **Data:** All raw competition data is sourced from  
  [`CharlieGnomo/champions_uefa_data`](https://github.com/CharlieGnomo/champions_uefa_data).  
- **Rules background:** Changes to the away goals rule are documented by UEFA and various football media outlets.
- **Tools:** The environment is managed via [`uv`](https://docs.astral.sh/uv/), with analysis performed in Jupyter notebooks using the standard Python data stack.

If you use this project or the underlying data in your own work, please make sure to credit the original data source and respect its license.
