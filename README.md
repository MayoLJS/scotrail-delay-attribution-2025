# ScotRail 2025 Performance Audit: A Data-Driven Analysis of Delay Attribution

## Project Objective
The primary goal of this project was to clean and analyze ScotRail 2025 performance data to identify the root causes of rail delays and determine organizational accountability. Using data from the Office of Rail and Road (ORR), I transformed raw periodic statistics into a structured format to uncover performance trends and the primary drivers of delay minutes.

## The Dataset
The analysis used Table 3184, which provides periodic delay minutes by operator and cause. The raw data was heavily structured in a "wide" format, with multiple columns representing different delay categories, requiring significant reshaping for effective analysis.

## Technical Workflow
* **Data Cleaning & Standardization:** Filtered the dataset to isolate ScotRail’s 2024–2025 financial year data. Standardized column headers by converting them to lowercase and removing parentheses.
* **Feature Engineering:** Used regular expressions (regex) to extract numeric values for the "Period" (e.g., Period 04) and "Financial Year" from the raw time-period strings to enable chronological sorting.
* **Data Reshaping (Unpivoting):** Utilized the `melt` function to transform the data from a wide format into a long format. This created a single `delay_cause` column and a `minutes` column, making the data compatible with categorical plotting libraries like Seaborn.
* **Responsibility Mapping:** Implemented a custom Python function to categorize specific delay causes into three high-level buckets: Network Rail (Infrastructure), ScotRail (Operational), and External/Other Operators.



## Key Insights
* **Primary Delay Drivers:** The leading cause of delays was **Network Management Other**, totaling **244,642 minutes**, followed by **Non-Track Assets** at **218,478 minutes**.
* **Organizational Accountability:** Infrastructure issues managed by **Network Rail** accounted for the largest share of delay minutes (**886,905.9**), while **ScotRail’s** own operational issues contributed **636,614.3 minutes**.
* **Temporal Trends:** Performance data for 2024–2025 highlighted a significant spike in delays during **Period 08**, where total delay minutes peaked at over **100,000**.

## Visualizations
* **Top 5 Causes of ScotRail Delays:** A bar chart highlighting the dominance of infrastructure-related issues.
* **High-Level Responsibility Breakdown:** A comparison of total delay minutes attributed to Network Rail vs. ScotRail operations.
* **2024-2025 Total Delay Minutes Trend:** A chronological view showing performance volatility throughout the financial year, including the major spike in late 2024.

## Tools & Libraries
* **Python:** Main language for processing.
* **Pandas:** Data cleaning, unpivoting, and aggregation.
* **Matplotlib & Seaborn:** Data visualization.
* **Regular Expressions (re):** Feature extraction from text strings.
