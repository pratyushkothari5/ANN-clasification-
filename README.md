# ANN Customer Churn Classification

This project predicts whether a bank customer is likely to churn using an
Artificial Neural Network (ANN) built with TensorFlow/Keras. It includes the
training and experimentation notebooks, saved preprocessing artifacts, and a
Streamlit interface for interactive predictions.

## Features

- Binary churn classification using customer demographic and account data.
- Categorical preprocessing:
  - Label encoding for gender.
  - One-hot encoding for geography.
- Feature standardization with `StandardScaler`.
- TensorFlow/Keras ANN model with early stopping and TensorBoard logging.
- Streamlit application for interactive churn-probability predictions.
- Supporting notebooks for training, prediction, hyperparameter tuning, and
  salary-regression experimentation.

## Project files

| File | Description |
| --- | --- |
| `app.py` | Streamlit prediction application |
| `Churn_Modelling.csv` | Customer churn dataset |
| `experiments.ipynb` | ANN training and TensorBoard experiments |
| `prediction.ipynb` | Example preprocessing and prediction workflow |
| `hyperparametertuningann.ipynb` | Hyperparameter-tuning experiments |
| `salaryregression.ipynb` | Regression experiment using the same dataset |
| `model.h5` | Trained churn-classification model |
| `regression_model.h5` | Trained regression model |
| `label_encoder_gender.pkl` | Fitted gender encoder |
| `onehot_encoder_geo.pkl` | Fitted geography encoder |
| `scaler.pkl` | Fitted feature scaler |
| `requirements.txt` | Python dependencies |

## Setup

Python 3.10 or newer is recommended.

```bash
git clone https://github.com/pratyushkothari5/ANN-clasification-.git
cd ANN-clasification-

python -m venv .venv
```

Activate the virtual environment:

**Windows PowerShell**

```powershell
.venv\Scripts\Activate.ps1
```

**macOS/Linux**

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Run the Streamlit app

Run the command from this project directory so the model and preprocessing
files are found:

```bash
streamlit run app.py
```

The app accepts geography, gender, age, balance, credit score, salary, tenure,
number of products, credit-card status, and active-member status. It displays
the predicted churn probability and a churn-risk message.

## TensorBoard

The training notebook writes TensorFlow event files under `logs/fit`. Run the
training cell before opening TensorBoard:

```bash
tensorboard --logdir logs/fit
```

For the salary-regression experiment, use:

```bash
tensorboard --logdir regressionlogs/fit
```

## Reproducibility

The `.pkl` files and trained models are included so the Streamlit app can run
without retraining. If you retrain the model, regenerate the encoders and
scaler in the same preprocessing run and keep them aligned with the model's
feature order.

## Dataset

The project uses the public `Churn_Modelling.csv` dataset. The target column is
`Exited`, where `1` indicates churn and `0` indicates that the customer did not
churn.

## License

This project is provided for educational and portfolio purposes.
