# 📊 Student Marks Analysis

A Python data analysis project that cleans, processes, and visualizes student marks data using **Pandas** and **Matplotlib**.

---

## 📁 Project Structure

```
student-analysis/
│
├── analysis.py       # Main script
└── README.md         # Project documentation
```

---

## 🔧 Requirements

- Python 3.7+
- pandas
- matplotlib

Install dependencies:

```bash
pip install pandas matplotlib
```

---

## 🚀 How to Run

```bash
python analysis.py
```

---

## 📌 What the Script Does

### 1. Dataset
Creates a sample dataset of 8 students with:
- `name` — Student name
- `marks` — Numeric marks (may contain invalid values like `'NaN'` or `'error'`)
- `city` — Student's city (may contain missing values)

### 2. Data Cleaning
- Converts `marks` column to numeric, replacing invalid entries (`'NaN'`, `'error'`) with `NaN`
- Fills missing `city` values with `'Unknown'`
- Drops rows where `marks` could not be parsed

### 3. Feature Engineering
| Column   | Description                                      |
|----------|--------------------------------------------------|
| `grade`  | `Low` (≤70), `Medium` (71–85), `High` (86–100)  |
| `status` | `Pass` if marks ≥ 75, else `Fail`               |

### 4. Analysis
- **Average marks** across all students
- **City-wise average marks**
- **Top scorer** — student with the highest marks
- **City with the most students**
- **Pass percentage**

### 5. Visualizations
Four bar/histogram charts are generated:
1. Average marks by city
2. Grade distribution (Low / Medium / High)
3. Marks histogram
4. Pass vs Fail count

---

## 📊 Sample Output

```
Average Marks: 84.67

City-wise Average:
 city
Delhi     81.67
Mumbai    88.00
Patna     84.00

Top Student:
 name      E
 marks    95.0
 city    Delhi
 ...

City with Most Students: Delhi
Pass Percentage: 83.33
```

---

## 📝 Notes

- Students with unparseable marks (e.g., `'error'`, `'NaN'`) are automatically excluded from analysis.
- The `pd.cut()` bins are inclusive of the upper bound; a mark of exactly 70 falls into the `Low` grade.
