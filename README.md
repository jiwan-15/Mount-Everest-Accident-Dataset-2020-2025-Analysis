# Mount Everest Accident Data Analysis (2020–2025)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📑 Table of Contents

* [Project Overview](#-project-overview)
* [Project Objectives](#-project-objectives)
* [Dataset](#️-dataset)
* [Data Cleaning](#-data-cleaning)
* [Feature Engineering](#-feature-engineering)
* [Analysis Performed](#-analysis-performed)

  * [Annual Accident Trends](#1-annual-accident-trends)
  * [Causes of Death](#2-causes-of-death)
  * [Altitude Analysis](#3-altitude-analysis)
  * [Death Zone Analysis](#4-death-zone-analysis)
  * [Seasonal Analysis](#5-seasonal-analysis)
  * [Weather Conditions](#6-weather-conditions)
  * [Experience Level](#7-experience-level)
  * [Gender Analysis](#8-gender-analysis)
  * [Route Analysis](#9-route-analysis)
  * [Nationality Analysis](#10-nationality-analysis)
  * [Expedition Company Analysis](#11-expedition-company-analysis)
* [Deep-Dive Analysis](#-deep-dive-analysis)
* [Visualisations](#-visualisations)
* [Tools & Technologies](#️-tools--technologies)
* [Project Structure](#-project-structure)
* [Example Python Code](#-example-python-code)
* [Key Insights](#-key-insights)
* [Limitations](#️-limitations)
* [Future Improvements](#-potential-future-improvements)
* [Conclusion](#-conclusion)
* [Author](#-author)
* [License](#-license)

---

## 📊 Project Overview

This project analyses **500 recorded Mount Everest accident records from 2020 to 2025** to identify patterns and trends associated with accidents and fatalities.

The analysis uses **Python, Pandas, NumPy, Matplotlib and Seaborn** to clean the dataset, perform exploratory data analysis (EDA), identify key patterns and create visualisations.

The project focuses on understanding how factors such as **year, altitude, cause of death, season, weather conditions, experience level, gender, route, nationality, location and expedition company** are represented within the recorded accident data.

> **Important:** This dataset contains accident records rather than the total number of climbers or expeditions. Therefore, the analysis identifies **recorded accident patterns and counts**, rather than calculating actual accident probabilities or risk rates.

---

## 🎯 Project Objectives

The main objectives of this project are to:

* Clean and prepare the raw dataset for analysis
* Assess data quality and identify missing or duplicate records
* Analyse annual accident trends from 2020–2025
* Identify the most common causes of death
* Investigate accidents by altitude
* Analyse accidents occurring above 8,000 metres
* Examine seasonal accident patterns
* Investigate the relationship between weather conditions and accidents
* Analyse accident records by experience level
* Compare accident records by gender
* Analyse routes and locations associated with recorded accidents
* Explore nationality and expedition company patterns
* Identify relationships between altitude and causes of death
* Create clear and accessible data visualisations
* Develop insights from the analysis

---

## 🗂️ Dataset

The dataset contains **500 records and 13 original columns**.
* **Mount Everest Accident Dataset (2020–2025):** Created by [Syed Muhammad Bilal](https://www.kaggle.com/syedmuhammadbilal12) and hosted on [Kaggle](https://www.kaggle.com/datasets/syedmuhammadbilal12/mount-everest-accident-dataset-2020-2025).

### Original Columns

| Column               | Description                          |
| -------------------- | ------------------------------------ |
| `Date`               | Date of the recorded incident        |
| `Name`               | Name of the individual               |
| `Nationality`        | Nationality                          |
| `Age`                | Age of the individual                |
| `Gender`             | Gender                               |
| `Cause_of_Death`     | Recorded cause of death              |
| `Altitude_meters`    | Recorded altitude in metres          |
| `Location`           | Location where the incident occurred |
| `Route`              | Mount Everest climbing route         |
| `Season`             | Season of the incident               |
| `Weather_Conditions` | Weather conditions                   |
| `Experience_Level`   | Climbing experience category         |
| `Expedition_Company` | Expedition company                   |

---

## 🧹 Data Cleaning

The raw dataset was inspected and prepared before analysis.

### Data-cleaning steps included:

* Checked dataset dimensions
* Inspected column names and data types
* Checked for missing values
* Checked for duplicate records
* Converted `Date` to datetime format
* Standardised text fields by removing unnecessary whitespace
* Converted numerical columns to appropriate numeric data types
* Validated age values
* Validated altitude values
* Created additional analytical variables

### Data Quality Summary

| Check            |       Result |
| ---------------- | -----------: |
| Records          |          500 |
| Original columns |           13 |
| Missing values   |            0 |
| Duplicate rows   |            0 |
| Invalid dates    |            0 |
| Age range        |        20–69 |
| Altitude range   | 5,364–8,848m |

---

## 🔧 Feature Engineering

Several new variables were created to support deeper analysis.

### `Year`

Extracted from the `Date` column to enable annual trend analysis.

### `Month`

Extracted from the `Date` column to support time-based analysis.

### `Altitude_Band`

Altitude was grouped into:

* `<6,000m`
* `6,000–6,999m`
* `7,000–7,999m`
* `8,000m+`

### `Age_Group`

Age was grouped into:

* `20–29`
* `30–39`
* `40–49`
* `50–59`
* `60+`

### `Death_Zone`

Records were categorised as:

* `Death Zone (8,000m+)`
* `Below Death Zone`

---

## 📈 Analysis Performed

### 1. Annual Accident Trends

The number of recorded accidents was analysed for each year from 2020 to 2025.

| Year | Recorded Accidents |
| ---: | -----------------: |
| 2020 |                 86 |
| 2021 |                 93 |
| 2022 |                 92 |
| 2023 |                 86 |
| 2024 |                 73 |
| 2025 |                 70 |

The highest number of recorded accidents occurred in **2021**, with 93 records.

Recorded accidents subsequently declined to 70 in 2025.

---

### 2. Causes of Death

The analysis identified the most frequently recorded causes of death.

| Cause                             | Records |
| --------------------------------- | ------: |
| Altitude Sickness (AMS/HAPE/HACE) |     129 |
| Exhaustion                        |      81 |
| Falling                           |      58 |
| Hypothermia                       |      42 |
| Avalanche                         |      36 |

Altitude sickness accounted for **25.8% of all records**.

Altitude sickness and exhaustion combined accounted for approximately **42% of the dataset**.

---

### 3. Altitude Analysis

| Altitude Band | Records |
| ------------- | ------: |
| <6,000m       |      24 |
| 6,000–6,999m  |      76 |
| 7,000–7,999m  |      56 |
| 8,000m+       |     344 |

A total of **344 records, or 68.8%**, occurred at 8,000 metres or above.

---

### 4. Death Zone Analysis

| Zone                 | Records | Percentage |
| -------------------- | ------: | ---------: |
| Death Zone (8,000m+) |     344 |      68.8% |
| Below Death Zone     |     156 |      31.2% |

The majority of recorded incidents occurred at or above 8,000 metres.

---

### 5. Seasonal Analysis

| Season | Records |
| ------ | ------: |
| Summer |     193 |
| Winter |     128 |
| Spring |      91 |
| Autumn |      88 |

Summer had the highest number of recorded accidents.

However, this should **not** be interpreted as meaning that summer has the highest accident rate because the dataset does not contain the total number of climbers or expeditions by season.

---

### 6. Weather Conditions

| Weather Condition | Records |
| ----------------- | ------: |
| Extreme cold      |      75 |
| Mixed conditions  |      66 |
| High winds        |      63 |
| Cloudy            |      63 |
| Blizzard          |      60 |

Extreme cold had the highest number of recorded cases.

---

### 7. Experience Level

The highest number of recorded accidents was associated with:

**Novice (First 8000m peak): 94 records**

However, the differences between experience groups were relatively modest. The results therefore do not demonstrate that experience level alone explains accident occurrence.

---

### 8. Gender Analysis

| Gender | Records |
| ------ | ------: |
| Male   |     252 |
| Female |     248 |

The difference between the two groups is only four records.

---

### 9. Route Analysis

The highest recorded accident count was:

**East Face — 88 records**

Other routes had relatively similar numbers of recorded incidents.

Because the dataset does not contain the number of climbers using each route, these figures should be interpreted as **recorded accident counts rather than route-specific risk rates**.

---

### 10. Nationality Analysis

The highest recorded counts included:

* Switzerland
* South Africa
* United States
* South Korea
* Russia

These results do not indicate that individuals from one nationality are inherently more likely to experience an accident. A meaningful risk comparison would require the total number of climbers from each nationality.

---

### 11. Expedition Company Analysis

The project also examined recorded accidents by expedition company.

The highest recorded counts included:

* Climbing the Seven Summits
* International Mountain Guides
* Furtenbach Adventures
* Peak Freaks
* Mountain Madness

These figures represent **recorded accident counts**, not company accident rates.

A fair comparison would require the number of clients or expeditions managed by each company.

---

## 🔍 Deep-Dive Analysis

The project investigates relationships between multiple variables, including:

* Altitude vs Cause of Death
* Season vs Cause of Death
* Weather vs Cause of Death
* Altitude vs Weather
* Experience Level vs Accident Count
* Route vs Accident Count
* Weather vs Altitude Sickness
* Age vs Altitude
* Multiple-variable combinations

One particularly important finding is that **altitude sickness becomes more prominent among records at 8,000m+**.

---

## 📊 Visualisations

The project includes visualisations such as:

* Annual accident trend
* Cause of death bar chart
* Accidents by altitude band
* Death Zone comparison
* Seasonal accident analysis
* Weather condition analysis
* Experience-level comparison
* Gender comparison
* Route analysis
* Age distribution
* Age-group analysis
* Cause vs altitude heatmap
* Season vs cause heatmap
* Weather vs cause heatmap

---

## 🛠️ Tools & Technologies

### Programming Language

* Python 3.8+

### Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn

### Development Environment

* Jupyter Notebook

### Version Control

* Git
* GitHub

---

## 📁 Project Structure

```text
Mount-Everest-Accident-Analysis/
│
├── Data/
│   ├── Mount Everest Accident Dataset 2020-2025.csv
│   └── Mount_Everest_Accident_Cleaned_2020_2025.csv
│
├── Mount_Everest_Accident_Analysis.ipynb
│
└── README.md
```

### Dataset Files

**Original dataset**

The original dataset is preserved without modification.

**Cleaned dataset**

The cleaned dataset contains the prepared data and additional analytical columns used throughout the project.

---

## 💻 Example Python Code

### Loading the Data

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv(
    "Mount Everest Accident Dataset 2020-2025.csv"
)

df.head()
```

### Creating the Cleaned Dataset

```python
df_clean = df.copy()

df_clean['Date'] = pd.to_datetime(
    df_clean['Date'],
    errors='coerce'
)

text_columns = df_clean.select_dtypes(
    include='object'
).columns

for column in text_columns:
    df_clean[column] = (
        df_clean[column]
        .astype(str)
        .str.strip()
    )
```

### Creating the Year Column

```python
df_clean['Year'] = df_clean['Date'].dt.year
```

### Creating Altitude Groups

```python
df_clean['Altitude_Band'] = pd.cut(
    df_clean['Altitude_meters'],
    bins=[0, 5999, 6999, 7999, 8848],
    labels=[
        '<6,000m',
        '6,000–6,999m',
        '7,000–7,999m',
        '8,000m+'
    ]
)
```

### Annual Accident Analysis

```python
annual_accidents = (
    df_clean
    .groupby('Year')
    .size()
    .reset_index(name='Accidents')
)

annual_accidents
```

### Visualisation

```python
plt.figure(figsize=(10, 5))

sns.lineplot(
    data=annual_accidents,
    x='Year',
    y='Accidents',
    marker='o'
)

plt.title('Everest Accidents by Year')
plt.xlabel('Year')
plt.ylabel('Number of Accidents')

plt.show()
```

---

## 💡 Key Insights

1. **Recorded accidents declined after 2021**, falling from 93 records in 2021 to 70 in 2025.
2. **Altitude sickness was the most frequently recorded cause**, accounting for 25.8% of records.
3. **68.8% of recorded incidents occurred at 8,000m or above.**
4. **Altitude sickness and exhaustion together represented approximately 42% of records.**
5. **Summer had the highest number of recorded incidents**, although this does not establish a higher accident rate.
6. **Extreme cold was the most frequently recorded weather condition.**
7. **Novice climbers had the highest recorded accident count among experience categories.**
8. **Male and female records were almost evenly distributed.**
9. **Route and expedition-company comparisons require exposure data before meaningful risk rates can be calculated.**
10. The analysis demonstrates the importance of distinguishing **accident counts from accident rates**.

---

## ⚠️ Limitations

This analysis has several important limitations.

### No Exposure Data

The dataset does not provide:

* Total number of climbers
* Number of expeditions
* Number of climbers per route
* Number of climbers per nationality
* Number of clients per expedition company
* Time spent at altitude

Therefore, the analysis cannot calculate true accident probabilities or rates.

### Recorded Incidents vs Population Risk

A higher accident count does not necessarily mean a higher risk.

For example:

> A route with more recorded accidents may simply have more climbers using it.

### Dataset-Specific Characteristics

The dataset should be treated as the source for this portfolio analysis. Findings should not automatically be interpreted as official Mount Everest statistics.

---

## 🚀 Potential Future Improvements

Future versions of the project could incorporate:

* Number of climbers by year
* Number of expeditions by year
* Route traffic/exposure
* Weather duration and severity
* Rescue and evacuation data
* Summit success rates
* Oxygen usage
* Previous climbing history
* Acclimatisation periods
* Geographic nationality exposure data

These additional variables would allow more meaningful **risk-rate and predictive analysis**.

---

## 📌 Conclusion

This project demonstrates an end-to-end data analysis workflow using Python, beginning with raw data inspection and cleaning and progressing through exploratory analysis, feature engineering, visualisation and interpretation.

The strongest pattern identified is the concentration of recorded accidents at extreme altitude, with **68.8% of records occurring at 8,000 metres or above**. Altitude sickness was also the leading recorded cause, representing **25.8% of all records**.

The project also demonstrates an important analytical principle: **recorded accident counts should not automatically be interpreted as accident rates** without appropriate exposure data.

Overall, the analysis provides a structured example of how data analytics can be used to uncover patterns, communicate findings and identify limitations within a real-world-style dataset.

---

## 👤 Author

**Jiwan Gurung**
* **LinkedIn:** [Jiwan Gurung](https://www.linkedin.com/in/jiwan-gurung-792088124/) 

---

## 📜 License

This project is licensed under the **MIT License**.

---

## Acknowledgments & AI Usage

AI tools were used to support the data analysis, processing, and visualisation for this project. All methodologies, findings, and final results were independently reviewed and validated by the author.

# Mount-Everest-Accident-Dataset-2020-2025-Analysis
