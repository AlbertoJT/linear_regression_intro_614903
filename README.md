# Linear Regression Intro — Students

Hands-on lab template for the Linear Regression class. Follow along with the instructor and complete the empty cells in each notebook.

## Project Structure

**Linear regression lab**
- `fundamentos_regresion_lineal.ipynb`: Theory — OLS, coefficients and assumptions
- `mpg_case/regression_on_mpg.ipynb`: 🎯 Hands-on lab — predict fuel efficiency (MPG): EDA, simple and multiple regression, VIF + p-values and RFECV

**Extra practice**
- `diamonds_case/regression_on_diamonds.ipynb`: Predict diamond prices
- `california_case/vif_pvalue_selection.ipynb`: Variable selection with VIF and p-values (California Housing)

**Environment**
- `pyproject.toml` / `uv.lock`: Project dependencies and the exact pinned versions
- `.python-version`: Exact Python version used everywhere
- `.devcontainer/`: GitHub Codespaces / Dev Container configuration

Each notebook starts with a "Preparación" section with helper functions: run those cells once and then just call the functions.

The SQLite databases are downloaded automatically by the notebooks (they are not versioned).

## Tools and Technologies

- Python 3.14 (exact version in `.python-version`)
- [uv](https://docs.astral.sh/uv/) to manage Python and dependencies
- Jupyter Notebooks (VS Code + Jupyter extension)
- pandas, NumPy, SciPy, scikit-learn, statsmodels, Plotly

## Environment

The local environment and GitHub Codespaces are built from the same files, so they are identical:

- `.python-version` pins the exact Python version (installed by uv, same build on every machine).
- `uv.lock` pins the exact version of every package.
- Codespaces runs `uv sync --frozen` when the container is created, which is the same command used locally.

### Option A: GitHub Codespaces (recommended)

Click **Code → Codespaces → Create codespace on main**. When the setup finishes, open any notebook and select the `.venv` kernel.

### Option B: Local

1. Install uv:
   ```bash
   # macOS
   brew install uv

   # Windows (PowerShell)
   powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

2. Clone this repository and create the environment:
   ```bash
   git clone https://github.com/jorgermzg15/modelos-predictivos-students.git
   cd modelos-predictivos-students
   uv sync --frozen
   ```

3. Open the folder in VS Code and select the `.venv` interpreter/kernel in the notebooks.

### Updating dependencies (instructor)

```bash
uv lock --upgrade   # resolve the newest compatible versions
uv sync --frozen    # apply them locally
```

Commit `uv.lock` (and `.python-version` if you change it). Codespaces will pick up the same versions on the next rebuild.

## Troubleshooting

1. Make sure the notebook kernel is the project's `.venv` (not a Conda/Anaconda environment).
2. If the environment gets out of sync, recreate it:
   ```bash
   rm -rf .venv
   uv sync --frozen
   ```
3. In Codespaces, if something breaks after changing `.devcontainer/`, run **Codespaces: Rebuild Container** from the command palette.

## For Students

1. Follow the environment instructions carefully
2. Execute the notebook cells in order
3. Complete the cells marked with ✍️ following the hints in each one
4. Experiment with the code and parameters to deepen your understanding

## License

This project is available for educational purposes. Feel free to use and learn from it!

## Database Credits

The SQLite databases used in this project are sourced from the [SQLite Databases for Learning Data Science](https://github.com/davidjamesknight/SQLite_databases_for_learning_data_science) repository by David James Knight.
