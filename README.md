# 🌿 Village Water Usage Analysis System

**A Real-Life Data Analysis Project Using Python, Pandas, and NumPy**

---

## 📘 Project Overview

This project analyzes **daily water usage patterns** in a village to ensure efficient and sustainable water management.
Using Python libraries like **Pandas** and **NumPy**, it performs:

* Per-household water usage calculation
* Classification of water usage levels
* Rainfall impact analysis
* Simple prediction for next day usage

It demonstrates how **data science can solve real-world rural challenges** like water shortage and wastage.

---

## ⚙️ Technologies Used

| Tool / Library | Purpose                                   |
| -------------- | ----------------------------------------- |
| Python         | Core programming language                 |
| Pandas         | Data analysis and manipulation            |
| NumPy          | Mathematical and statistical calculations |

---

## 🧩 Features

✅ Calculates average water usage per household
✅ Classifies usage as **Low**, **Normal**, or **High**
✅ Analyzes effect of rainfall on water consumption
✅ Predicts next day’s estimated usage
✅ Helps promote water conservation in rural communities

---

## 🧠 Dataset Example

| Date       | Village_Name | Households | Total_Water_Used(L) | Rainfall(mm) |
| ---------- | ------------ | ---------- | ------------------- | ------------ |
| 2025-06-01 | Rampur       | 120        | 5400                | 2.5          |
| 2025-06-02 | Rampur       | 120        | 6200                | 0.0          |
| 2025-06-03 | Rampur       | 120        | 4800                | 5.0          |

---

## 🧮 Core Python Code Snippet

```python
import pandas as pd
import numpy as np

data = {
    'Date': pd.date_range(start='2025-06-01', periods=7, freq='D'),
    'Village_Name': ['Rampur']*7,
    'Households': [120]*7,
    'Total_Water_Used(L)': [5400,6200,4800,5000,5500,5300,4900],
    'Rainfall(mm)': [2.5,0.0,5.0,3.0,0.0,1.0,4.0]
}

df = pd.DataFrame(data)
df['Avg_Water_Per_Household'] = df['Total_Water_Used(L)'] / df['Households']

avg_usage = np.mean(df['Avg_Water_Per_Household'])
std_usage = np.std(df['Avg_Water_Per_Household'])
min_usage = avg_usage - std_usage
max_usage = avg_usage + std_usage

def classify_usage(x):
    if x < min_usage:
        return 'Low'
    elif x > max_usage:
        return 'High'
    else:
        return 'Normal'

df['Usage_Level'] = df['Avg_Water_Per_Household'].apply(classify_usage)
print(df)
```

---

## 📊 Sample Output

| Date       | Avg_Water_Per_Household | Usage_Level |
| ---------- | ----------------------- | ----------- |
| 2025-06-01 | 45.0                    | Normal      |
| 2025-06-02 | 51.7                    | High        |
| 2025-06-03 | 40.0                    | Low         |

---

## 📈 Insights

* Water consumption decreases on **rainy days**
* A few days show **over-usage**, which can be optimized
* The system helps local authorities **predict and plan** water distribution

---

## 🧩 How to Run the Project

1. Install Python (>=3.8)
2. Install required libraries:

   ```bash
   pip install pandas numpy
   ```
3. Save the Python file (e.g., `village_water_analysis.py`)
4. Run:

   ```bash
   python village_water_analysis.py
   ```

---

## 🚀 Future Scope

* Add **data visualization** using Matplotlib or Seaborn
* Include **multiple villages** and compare patterns
* Integrate **IoT sensors** for real-time data collection
* Extend to **machine learning models** for water demand forecasting

---

## 👩‍💻 Author

**Sanjana Sherawat**
📚 MCA Student, Lovely Professional University
🎓 Microsoft Learn Student Ambassador

---

## ⭐ Contribution

If you like this project, give it a **star ⭐** on GitHub and share your feedback!

---

> “A drop of data can save a drop of water.” 💧

