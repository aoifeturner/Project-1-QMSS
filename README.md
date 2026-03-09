# World Happiness Classification Competition 

QMSS GR5074 project: classify countries into happiness categories using the World Happiness Report 2023 and socioeconomic data.

## What’s in this repo

- **Project.ipynb** — Main Jupyter notebook (data load, EDA, preprocessing, models, SHAP, ensemble).
- **data/** — Folder for input CSVs. You must add:
  - `WHR_2023.csv`
  - `newcountryvars.csv`
- **artifacts/** — Created when you run the notebook (saved preprocessor and models).

## Requirements

- Python 3.10 or 3.11 (3.12 may work; TensorFlow/SHAP support varies)
- Dependencies listed in `requirements.txt`:
  - **pandas** — Data load and manipulation  
  - **numpy** — Numerical arrays  
  - **scikit-learn** — Preprocessing, models, metrics, GridSearchCV  
  - **matplotlib** — Plotting  
  - **tensorflow** — Keras models (neural networks)  
  - **shap** — SHAP feature importance  
  - **jupyter**, **ipykernel** — Run the notebook

## How to run

### 1. Clone or download the project

Make sure the project folder contains `Project.ipynb`, `requirements.txt`, and a `data` folder.

### 2. Create a virtual environment (recommended)

From the project root (the folder that contains `Project.ipynb` and `requirements.txt`):

**Windows (Command Prompt or PowerShell):**

```bash
python -m venv venv
venv\Scripts\activate
```

**macOS / Linux:**

```bash
python3 -m venv venv
source venv/bin/activate
```

Your prompt should show `(venv)` when the environment is active.

### 3. Install the requirements inside the venv

With the venv activated:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Register the venv as a Jupyter kernel (so you can run the notebook with this env)

Still with the venv activated:

```bash
python -m ipykernel install --user --name=project-venv --display-name "Python (project-venv)"
```

### 5. Run the notebook

- Open Jupyter:  
  `jupyter notebook`  
  or open **Project.ipynb** in VS Code / Cursor.
- If you use Jupyter in the browser: open `Project.ipynb`, then in the menu choose **Kernel → Change kernel → Python (project-venv)** (or the name you used in step 4).
- Run all cells (e.g. **Cell → Run All**).  
  The notebook will read from `data/`, run the full pipeline, and write preprocessor/model artifacts into `artifacts/` when relevant.

## Optional: Install without a venv

If you prefer not to use a virtual environment:

```bash
pip install --upgrade pip
pip install -r requirements.txt
jupyter notebook
```

Then open `Project.ipynb` and run all cells. Data must still be in the `data/` folder.

## Notes

- The notebook expects to find **WHR_2023.csv** and **newcountryvars.csv** in a **data** folder next to the notebook. Paths used in code are `data/WHR_2023.csv` and `data/newcountryvars.csv`.
- Some cells (e.g. SHAP, saving models) use an **artifacts** directory; the notebook creates it when needed.
- TensorFlow can be heavy; first run may be slower while dependencies load. Using a GPU is optional.
