# A/B Test Analysis: Impact of Personalized Messaging

This project analyzes the effectiveness of **personalized vs. generic messages** on user engagement. The analysis includes a **PySpark-based data pipeline** and a **Python-based statistical test** using a Z-test to determine if personalization significantly improves engagement rates.

---

## Objective

To evaluate whether personalized messages lead to higher user engagement than generic messages through A/B testing and statistical validation.

---

## Dataset Overview

The dataset contains user-level interaction logs with the following columns:

- `user_id`: Unique identifier
- `message_type`: 'Personalized' or 'Generic'
- `engaged`: Boolean flag indicating user engagement
- `total_messages_seen`: Total messages seen by the user
- `most_engagement_weekday`, `most_engagement_hour`: Temporal behavior features

---

## Data Processing with PySpark

We used **PySpark** to process and clean the data efficiently at scale:

- Dropped nulls in key columns (`user_id`, `message_type`)
- Removed users assigned to both test groups to preserve test validity
- Handled duplicates by keeping the first occurrence per user and group
- Converted boolean `engaged` to numeric (0/1)
- Aggregated data to calculate engagement rate per group

Notebook: [`01_data_cleaning_pyspark.ipynb`](notebooks/01_data_cleaning_pyspark.ipynb)

---

## Statistical Analysis with Python

Performed with `pandas` and `statsmodels`:

- **Power Analysis** to calculate required sample size using `statsmodels`
  > Required ~9,848 users per group to detect a +0.5% lift with 80% power


- **Two-proportion Z-test** comparing engagement between groups
  > - p-value < 0.0000017  
  > Statistically significant

- Calculated **Confidence Interval (95%)** for absolute lift
  > - Absolute Lift: +0.77%  
  > - CI Range: [+0.60%, +0.94%]
  


Notebook: [`02_statistical_analysis_python.ipynb`](notebooks/02_statistical_analysis_python.ipynb)

---

## Visualizations

### 1. **Engagement Rate per Group**
Bar chart comparing `Generic` vs `Personalized`

### 2. **Confidence Interval Plot**
Error bar showing:
- Absolute Lift = 0.77%
- Confidence interval range: [0.60%, 0.94%]

### 3. **Power Curve (optional)**
Power vs Sample Size curve to show how power changes with user count

You can save these graphs as `.png` in the `charts/` folder and reference them in the README like:


---

## Business Insight
- Personalized messages led to a statistically significant +0.77% lift in engagement rate
- 95% CI: between +0.60% and +0.94%
- At this data scale (~588,000 users), this equals ~4,500 additional user engagements
- Strong evidence to recommend scaling personalization across campaigns

## Conclusion
This experiment demonstrates:
- Robust A/B testing design
- Statistical rigor using power analysis and confidence intervals
- Actionable business recommendation

## Repository Structure
ab-test-personalized-messaging/
├── notebooks/
│   ├── 01_data_cleaning_pyspark.ipynb
│   └── 02_statistical_analysis_python.ipynb
├── charts/    
└── README.md







[here](https://drive.google.com/file/d/1Dgrd8WjGkMHk8IVkioEECeAsPokpC0J8/view?usp=sharing).


