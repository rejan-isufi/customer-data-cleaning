# Customer Data Cleaning Project

Cleaning a messy 50-row customer dataset with Python and pandas in a Jupyter Notebook.

## 📁 Files

| File | Description |
| :--- | :--- |
| `customer_data_cleaning.ipynb` | Full cleaning workflow with explanations |
| `messy_customers.csv` | Raw dataset (50 rows, 5 columns) |
| `clean_customers.csv` | Cleaned dataset (48 rows, 5 columns) |

---

## 🛠️ Problems Found and Fixes Applied

| Problem | Fix |
| :--- | :--- |
| 2 duplicate rows | `drop_duplicates()` |
| Extra spaces and inconsistent capitalisation in names and cities | `str.strip()`, `str.title()` |
| 11 city spellings instead of 6 (Tirane, Durrës, TIRANA...) | `replace()` to merge variants |
| Dates in 4 different formats | Parsed each format explicitly with `pd.to_datetime` |
| Text in numeric columns ("27 years", "€57.22", "163.58 EUR", "45,5") | Regex and string cleaning, then `pd.to_numeric` |
| Impossible ages (250 and -4) | Treated as missing (valid range 18-100) |
| Extreme spend value (4999.99) | Detected with the IQR rule, treated as missing |
| Missing values | Names and cities set to "Unknown"; age and spend filled with the median; the one missing date left blank |

---

## 📊 Summary of Results

| Metric | Before | After |
| :--- | :---: | :---: |
| **Rows** | 50 | 48 |
| **Duplicate rows** | 2 | 0 |
| **Missing values** | 6 | 1 |
| **Unique cities** | 11 | 6 |

---

## 🧰 Tools
- Python
- pandas
- Jupyter Notebook

---

## 🚀 How to Run

1. Place `messy_customers.csv` in the same folder as the notebook.
2. Open `customer_data_cleaning.ipynb` in Jupyter Notebook and run all cells.
3. The cleaned file will be saved automatically as `clean_customers.csv`.
