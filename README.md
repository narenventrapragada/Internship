# 🧹 Data Cleaning Task – Dirty Dataset (200 Rows)

## 📂 Project Overview
This project involves cleaning a messy Excel dataset containing 200 customer order records. The data had multiple inconsistencies across date formats, text fields, numerical conversions, and missing values. The entire cleaning process was carried out using Python in a Jupyter Notebook (`Task1.ipynb`).

---

## 🗃️ Dataset Summary

### 📥 Raw Dataset: `dirty_dataset_200_rows.xlsx`
**Columns:**
- Order ID
- Customer Name
- Order Date
- Product
- Category
- Quantity
- Price
- Total
- Region

---

## 🧼 Cleaning Steps Performed

### 🔁 1. Duplicate Removal
- Removed exact duplicate rows using `df.drop_duplicates()`.

### ⚠️ 2. Missing Values
- Replaced missing `Customer Name` and `Region` with `"Unknown"`.
- Replaced empty strings in `Quantity` with 0.
- Used `ffill()` for blank or invalid values.

### 🧾 3. Text Cleaning
- Trimmed leading/trailing whitespaces in text fields.
- Standardized capitalization for `Customer Name`, `Category`, and `Region`.
- Used `.str.title()` and `.str.strip()` functions.

### 🔢 4. Quantity Cleanup
- Converted text values like `"two"`, `"Three"` to numeric using a custom mapping dictionary.
- Converted final column to `int` type.

### 💲 5. Price & Total Fix
- Ensured `Price` was numeric.
- Recalculated `Total = Quantity * Price`.

### 📅 6. Date Standardization
- The `Order Date` column contained formats like:
  - `01/05/2023`, `07-08-23`, `Oct 12, 2023`, `8/9/23`, `2023.11.01`
- Used `to_datetime(data['Order Date'])` with `format='mixed'` to handle all formats.
- Converted to datetime using a custom parser and standardized to `YYYY-MM-DD`.

### 📊 7. Category Normalization
- Mapped variants like `"Electrnics"`, `"Electronic"`, `"ElecTronics"` → `"Electronics"`.
- Used a dictionary to replace all inconsistencies.

---

## 🧪 Final Dataset: `cleaned_dataset.xlsx`
- All data types validated
- No duplicates
- Clean categories and regions
- Standardized dates
- Accurate totals

---

## 🛠 Technologies Used
- Python 3.x
- Jupyter Notebook
- pandas
- numpy
- dateutil

---

## 📁 Files
| Filename              | Description                         |
|-----------------------|-------------------------------------|
| `dirty_dataset_200_rows.xlsx` | Raw dataset before cleaning      |
| `Task1.ipynb`         | Jupyter Notebook with all cleaning steps |
| `cleaned_dataset.xlsx`| Final cleaned output dataset         |
| `README.md`           | Project summary and documentation   |

---

## ✅ How to Run
1. Open `Task1.ipynb` in Jupyter Notebook.
2. Ensure you have the required libraries:
   ```bash
   pip install pandas numpy python-dateutil openpyxl
