# 📊 Demographic Data Analysis with Pandas

This project analyzes demographic data from the 1994 U.S. Census using Python and Pandas. Key statistics about education, employment, and income are extracted.

## 📂 Project Structure

```
📂 demographic-data-analyzer
 ├── 📄 demographic_data_analyzer.py  # Main analysis script
 ├── 📄 test_module.py                # Test cases for analysis
 ├── 📄 README.md                     # Documentation
 ├── 📄 requirements.txt               # Required libraries
 ├── 📄 adult.data.csv                 # 1994 Census dataset
```

## 📝 Code Explanation

The `demographic_data_analyzer.py` script analyzes demographic data by answering key questions about the population.

### 📊 1. Average Age of Men
Calculates the average age of men in the dataset.

```python
average_age_men = df[df["sex"] == "Male"]["age"].mean().round(1)
```

### 🎓 2. Percentage of People with Advanced Education
Determines the percentage of people with a Bachelor's, Master's, or Doctorate degree.

```python
higher_education = df[df["education"].isin(["Bachelors", "Masters", "Doctorate"])]
higher_education_rich = round(len(higher_education[higher_education.salary == ">50K"]) / len(higher_education) * 100, 1)
```

### 💰 3. Country with the Highest Percentage of High Earners
Finds the country with the highest percentage of people earning more than $50K per year.

```python
country_count = df["native-country"].value_counts()
country_rich_count = df[df["salary"] == ">50K"]["native-country"].value_counts()

highest_earning_country = (country_rich_count / country_count).idxmax()
highest_earning_country_percentage = round((country_rich_count / country_count * 100).max(), 1)
```

### ⏳ 4. Working Hours and Income Level
Finds the maximum number of weekly working hours and the percentage of those workers earning more than $50K.

```python
max_work_hours = df["hours-per-week"].max()
num_rich_max_workers = len(df[(df["hours-per-week"] == max_work_hours) & (df["salary"] == ">50K")])
rich_percentage = round((num_rich_max_workers / len(df[df["hours-per-week"] == max_work_hours]) * 100), 1)
```

### 🏆 5. Highest-Paying Occupation in India
Identifies the most common occupation among high-income earners in India.

```python
top_IN_occupation = df[(df["native-country"] == "India") & (df["salary"] == ">50K")]["occupation"].mode()[0]
```

## ✅ Analysis Results

| 📌 Metric                              | 📊 Result        |
|--------------------------------------|----------------|
| 👨‍💼 Average age of men               | 39.4 years     |
| 🎓 % with advanced education (>50K)  | 46.5%         |
| 🌍 Country with highest % of rich    | Ireland (56.2%) |
| 💼 Highest-paying occupation in India | Prof-specialty |

These results provide a clear insight into the income demographics of 1994.

## 📜 License

This project is open-source and available under the MIT license.


