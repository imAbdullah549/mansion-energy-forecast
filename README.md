# mansion-energy-forecast
Time-series models (LSTM/GRU/TCN/Transformer) to forecast hourly electricity consumption of a mansion using weather &amp; calendar features, with strict Train/Test/Eval splits.

# Mansion Energy Forecast

Forecast hourly electricity consumption for a mansion using weather + calendar features.  
Built as a group project with a **shared data pipeline** and **four distinct models** (LSTM, GRU, TCN, Transformer).  
Evaluation follows strict time splits: Train, Test, and three seasonal Eval windows.

## 🚀 What’s inside
- **Shared pipeline**: clean → feature engineering → post-clean → fixed splits → train-only scaling
- **Baselines**: Naive (t−1), Seasonal Naive (t−168)
- **Models (one per teammate)**: LSTM, GRU, TCN, Transformer
- **Reports**: metrics table (MAE/RMSE) + example plots

## 📂 Project structure

```text
.
├─ data_raw/                  # put original CSV here (not committed)
├─ data_proc/                 # generated: clean & feature tables
├─ artifacts/                 # generated: scaler, feature list
├─ preds/                     # model predictions (CSV)
├─ reports/                   # results & figures
├─ src/
│  ├─ pipeline/               # run_all / clean / features / postclean / baselines / evaluate
│  ├─ models/                 # lstm_model.py, gru_model.py, tcn_model.py, transformer_model.py
│  └─ utils/                  # shared helpers (load_splits, make_sequences)
├─ config/                    # splits.json (time windows)
├─ notebooks/                 # ad-hoc analysis (optional)
├─ requirements.txt
└─ README.md



## 🧰 Requirements
- Python 3.10+
- `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `joblib`, `torch`

Install:
```bash
python -m venv .venv
# mac/linux
source .venv/bin/activate
# windows powershell
# .venv\Scripts\Activate.ps1

pip install -U pip
pip install -r requirements.txt
