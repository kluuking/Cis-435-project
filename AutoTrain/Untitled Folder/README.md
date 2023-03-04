---
tags:
- autotrain
- tabular
- classification
- tabular-classification
datasets:
- Kluuking/autotrain-data-test-3
co2_eq_emissions:
  emissions: 0.9466490190669987
---

# Model Trained Using AutoTrain

- Problem type: Binary Classification
- Model ID: 38732101859
- CO2 Emissions (in grams): 0.9466

## Validation Metrics

- Loss: 0.527
- Accuracy: 0.742
- Precision: 0.562
- Recall: 0.168
- AUC: 0.702
- F1: 0.258

## Usage

```python
import json
import joblib
import pandas as pd

model = joblib.load('model.joblib')
config = json.load(open('config.json'))

features = config['features']

# data = pd.read_csv("data.csv")
data = data[features]
data.columns = ["feat_" + str(col) for col in data.columns]

predictions = model.predict(data)  # or model.predict_proba(data)

```