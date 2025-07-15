# A/B Test Analysis: Impact of Personalized Messaging

This project analyzes an A/B test to determine if personalized messages increase user engagement compared to generic messages. The data processing pipeline is built with **PySpark** to efficiently handle and clean the dataset. The subsequent statistical analysis is performed in **Python**, utilizing libraries like `pandas` and `statsmodels` to conduct a Z-test and calculate confidence intervals.

The key outcome was a statistically significant finding. The analysis revealed a **+43.09% relative lift** in engagement. More specifically, we are 95% confident that personalized messages increase the absolute engagement rate by **+0.60% to +0.94%**.

## Project Structure
├── notebooks
│   ├── 01_data_processing_pyspark.ipynb  # Notebook for data cleaning, transformation, and aggregation.
│   └── 02_statistical_analysis.ipynb     # Notebook for statistical testing and interpretation.
└── README.md  # Project documentation.
The dataset used for this analysis is hosted on Google Drive due to its size. You can access it [here](https://drive.google.com/file/d/1Dgrd8WjGkMHk8IVkioEECeAsPokpC0J8/view?usp=sharing).


