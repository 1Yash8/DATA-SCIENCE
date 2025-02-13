## Overview
This repository contains step-by-step solutions and explanations for analyzing bakery sales data using Python and Pandas. The goal is to understand how to analyze data systematically and develop basic data science skills.

## Getting Started
This project is implemented in **Google Colab**, and no additional installation is required except for loading necessary libraries.

### Prerequisites
Ensure you have the following installed:
- **Google Colab** (Recommended)
- **Python 3.x**
- **Pandas** (Pre-installed in Google Colab)
- **Matplotlib** (For data visualization)

## Steps Covered So Far

### 1️⃣ Checking If Pandas Is Installed
```python
import pandas as pd  # Import pandas
print(pd.__version__)  # Check the installed version
```

### 2️⃣ Finding the Day with the Highest Pies Sold
#### Given Data:
| Day       | Pies Sold |
|-----------|-----------|
| Monday    | 5         |
| Tuesday   | 6         |
| Wednesday | 7         |
| Thursday  | 10        |
| Friday    | 15        |
| Saturday  | 18        |

#### Python Code:
```python
import pandas as pd

data = {
    "Day": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"],
    "Pies Sold": [5, 6, 7, 10, 15, 18]
}

df = pd.DataFrame(data)
max_pies_day = df.loc[df["Pies Sold"].idxmax(), "Day"]
print(f"The highest number of pies was sold on: {max_pies_day}")
```
✅ **Output:**
```
The highest number of pies was sold on: Saturday
```

### 3️⃣ Identifying Days Where More Than 60 Cookies Were Sold
#### Given Data:
| Day       | Cookies Sold |
|-----------|-------------|
| Monday    | 50          |
| Tuesday   | 55          |
| Wednesday | 52          |
| Thursday  | 60          |
| Friday    | 65          |
| Saturday  | 70          |

#### Python Code:
```python
import pandas as pd

data = {
    "Day": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"],
    "Cookies Sold": [50, 55, 52, 60, 65, 70]
}

df = pd.DataFrame(data)

high_cookie_sales = df[df["Cookies Sold"] > 60]  # Filter for Cookies Sold > 60
print("Days where more than 60 cookies were sold:")
print(high_cookie_sales["Day"].tolist())
```
✅ **Output:**
```
Days where more than 60 cookies were sold:
['Friday', 'Saturday']
```

### 4️⃣ Data Visualization (Optional)
```python
import matplotlib.pyplot as plt

plt.figure(figsize=(8, 5))
plt.bar(df["Day"], df["Cookies Sold"], color="lightcoral")
plt.axhline(y=60, color="red", linestyle="--", label="Threshold: 60")
plt.xlabel("Day of the Week")
plt.ylabel("Number of Cookies Sold")
plt.title("Cookies Sold Per Day")
plt.legend()
plt.show()
```
✅ This will generate a **bar chart** showing the sales of cookies per day, with a red dashed line at **60** to highlight the threshold.

## Next Steps
- Continue analyzing more sales trends using different statistical methods.
- Apply machine learning models to predict sales trends.
- Improve data visualization with **Seaborn** and **Matplotlib**.

## Contributing
Feel free to fork this repository, improve the code, and submit a pull request. Any contributions are welcome! 🚀

## License
This project is open-source and available under the **MIT License**.

---
### 🚀 Happy Coding! 🎯
