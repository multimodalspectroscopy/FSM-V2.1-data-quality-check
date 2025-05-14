# Data Quality Check

This repository provides functionality to compute and visualize various data quality metrics for LED detector signals. It includes Signal-to-Noise Ratio (SNR), Noise Equivalent Power (NEP), and Distance to Dark measurements, all visualized using Plotly charts.

---

## 📂 File Structure

```

data\_quality\_check/
├── **init**.py                 # Exposes the main function
└── data\_quality\_check.py       # Main logic for SNR, NEP, and visualization

````

---

## ✅ Features

- 📊 **SNR Histogram** – View SNR for all LED signal channels.
- 🎯 **Gauge Plot** – Visualize the SNR of a selected LED signal.
- 🧩 **Group-wise SNR and NEP** – Group signals and show comparative metrics.
- 🕒 **Time-based Scatter Plot** – Observe signal fluctuations over time.
- 🧮 **Distance to Dark Plot** – Calculate Euclidean distance from dark signal.

---

## 📦 Installation

```bash
git clone https://github.com/your-username/data_quality_check.git
cd data_quality_check
pip install numpy pandas plotly
````

---

## 🚀 Usage

```python
import pandas as pd
from src.data_quality_check import data_quality_check

# Load your data
df = pd.read_csv("your_data.csv")

# Choose a column to inspect
selected_column = "LED_A_808_DET1"

# Run the check
figs = data_quality_check(df, selected_column)

# Unpack and show figures
for fig in figs:
    fig.show()
```

---

## 📝 Data Requirements

Your input DataFrame should contain:

* A `Time` column. Time format here MM:SS:S  (Minutes, seconds and miliseconds)
* Signal columns such as `LED_A_808_DET1`.
* Corresponding dark signal columns, e.g. `LED_A_DARK_DET1`.

Signal-dark mappings are pre-defined in the function.

---

## 📊 Output Visualizations

* **SNR Histogram** – All signals
* **SNR Gauge** – Selected signal
* **Group SNR Bar Chart**
* **Group NEP Bar Chart**
* **Signal Time Scatter Plot**
* **Distance to Dark Line Plot**

---

## 📄 License

MIT License
