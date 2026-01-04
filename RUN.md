# How to Run the Student Performance Prediction Project

## Quick Start (All Steps)

### Step 1: Activate Virtual Environment

```bash
cd /Users/aadipratapsingh/Documents/student-performance-prediction-ml
source venv/bin/activate
```

You should see `(venv)` in your terminal prompt.

### Step 2: Generate Dataset (if not already done)

```bash
python3 src/create_dataset.py
```

This creates `data/student_data.csv` with 500 student records.

### Step 3: Train Models (if not already done)

```bash
python3 src/train_models.py
```

This will:
- Load and preprocess the data
- Train 3 models (Logistic Regression, Random Forest, Gradient Boosting)
- Compare their performance
- Save the best model to `models/` directory

### Step 4: Run Streamlit App

```bash
streamlit run app.py
```

The app will automatically open in your browser at `http://localhost:8501`

---

## Individual Component Instructions

### Option A: Run EDA Notebook

1. Start Jupyter:
   ```bash
   source venv/bin/activate
   jupyter notebook notebooks/01_eda.ipynb
   ```

2. Or use JupyterLab:
   ```bash
   jupyter lab notebooks/01_eda.ipynb
   ```

### Option B: Run Hyperparameter Tuning (Optional)

After training models, optimize them:

```bash
source venv/bin/activate
python3 src/hyperparameter_tuning.py
```

### Option C: Run Individual Scripts

**Create dataset only:**
```bash
source venv/bin/activate
python3 src/create_dataset.py
```

**Train models only:**
```bash
source venv/bin/activate
python3 src/train_models.py
```

**Run app only (requires trained models):**
```bash
source venv/bin/activate
streamlit run app.py
```

---

## Troubleshooting

### If virtual environment is not activated:
```bash
source venv/bin/activate
```

### If dependencies are missing:
```bash
source venv/bin/activate
pip install -r requirements.txt
```

### If dataset is missing:
```bash
python3 src/create_dataset.py
```

### If models are missing:
```bash
python3 src/train_models.py
```

### If Streamlit app shows "Model not found":
1. Make sure you've run `python3 src/train_models.py` first
2. Check that `models/` directory contains `.pkl` files

### To stop Streamlit app:
Press `Ctrl+C` in the terminal where Streamlit is running

---

## Expected Output

### After dataset creation:
- File: `data/student_data.csv` (500 rows)

### After model training:
- Files in `models/`:
  - `best_model.pkl`
  - `preprocessor.pkl`
  - `feature_names.pkl`
  - `numerical_cols.pkl`
  - `categorical_cols.pkl`

### Streamlit app:
- Opens at `http://localhost:8501`
- Interactive interface with sidebar for inputs
- Prediction button and results display

---

## Complete Workflow (One-time Setup)

```bash
# 1. Navigate to project
cd /Users/aadipratapsingh/Documents/student-performance-prediction-ml

# 2. Activate virtual environment
source venv/bin/activate

# 3. Generate dataset
python3 src/create_dataset.py

# 4. Train models
python3 src/train_models.py

# 5. (Optional) Tune hyperparameters
python3 src/hyperparameter_tuning.py

# 6. Run Streamlit app
streamlit run app.py
```

---

## Daily Usage (After Setup)

Once everything is set up, you only need:

```bash
source venv/bin/activate
streamlit run app.py
```

The app will load the pre-trained models and be ready for predictions!

