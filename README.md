## 📊 Uber Data Analysis Project

This project involves a detailed exploratory data analysis (EDA) of an Uber trip dataset using Python. The analysis covers data preprocessing, visualization, and insights derived from trip patterns based on time, purpose, and category.

---

### 📁 Dataset

* **File:** `UberDataset.csv`
* Contains Uber trip details including:

  * Start and end timestamps
  * Trip category (Business/Personal)
  * Purpose of trip
  * Distance traveled in miles

---

### 🛠️ Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from datetime import datetime
```

---

### 🧹 Data Preprocessing

* **Missing Values:** Filled missing `PURPOSE` values with `"NOT"`.
* **Date Conversion:** Converted `START_DATE` and `END_DATE` to datetime format.
* **Time Features:**

  * Extracted `date` and `hour` from `START_DATE`.
  * Categorized trips into `"Morning"`, `"Afternoon"`, `"Evening"`, and `"Night"` based on hour of the day.
* **Cleaning:**

  * Removed missing entries and duplicates.

---

### 📊 Data Visualization Highlights

#### ✅ Count of Trips by Category

```python
sns.countplot(x='CATEGORY', data=dataset, palette='viridis')
```

#### ✅ Count of Trips by Purpose

```python
sns.countplot(y='PURPOSE', data=dataset, order=dataset['PURPOSE'].value_counts().index)
```

#### ✅ Day vs Night Trip Distribution

```python
sns.countplot(dataset['day-night'], palette='viridis')
```

#### ✅ Comparing the two different categories along with the PURPOSE of the user

```python
sns.countplot(x='CATEGORY', hue='PURPOSE', data=dataset, palette='viridis')
```

#### ✅ Correlation Heatmap

```python
sns.heatmap(correlation_matrix, annot=True)
```

#### ✅ Monthly Ride Distribution

```python
sns.lineplot(data=monthly_df)
```

#### ✅ Day of Week Analysis

```python
sns.barplot(x=day_label.index, y=day_label)
```

#### ✅ Boxplot to check the distribution of the column.

```python
sns.boxplot(dataset['MILES'])
sns.distplot(dataset[dataset['MILES']<50]['MILES'])
```
#### ✅ Use distplot for values less than 40

```python
sns.distplot(dataset[dataset['MILES']<50]['MILES'])
```
---

### 📅 Feature Engineering

* Extracted **Month** and **Day of Week** from `START_DATE`.
* Mapped numerical month/day values to proper labels for better readability.

---

### 🔍 Insights You Can Extract

* Peak trip purposes by category
* Daily and monthly ride patterns
* Distance distribution trends
* Correlations between numerical features like `MILES` and trip timings

---

### 📌 How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/uber-data-analysis.git
   cd uber-data-analysis
   ```

2. Install dependencies (recommended: use a virtual environment):

   ```bash
   pip install -r requirements.txt
   ```

3. Run the Jupyter Notebook, Python script, Google Colab.

---

### 📂 Folder Structure (if applicable)

```
├── UberDataset.csv
├── Uber Rides Data Analysis.ipynb
├── README.md
```

---

### 🧾 License

This project is licensed under the MIT License.

---

