NEWS ANALYSIS DASHBOARD

**Tracking Fake VS Real News Trends**

📌 Overview
The **News Analysis Dashboard** is designed to provide an in-depth analysis of the distribution and trends of fake and real news articles. It helps identify patterns in misinformation by analyzing publication counts over time, by source, and by category.
The dashboard leverages **Power BI visualizations** to deliver clear, actionable insights for researchers, journalists, and policymakers.

---
📊 Key Features
* **Total Article Analysis** – Displays overall news count, split into real and fake news.
* **Fake vs Real News Distribution** – A donut chart showcasing the proportion of fake and real articles.
* **Trend Analysis** – Line chart showing fake news trends from 2022 to 2025.
* **Monthly Analysis** – Clustered bar chart comparing real and fake news counts per month.
* **Source Analysis** – Bar charts showing the number of fake and real articles for each news source.
* **Category Analysis** – Breakdown of fake and real news across categories like Health, Business, Entertainment, Sports, Technology, Politics, and Science.
* **Sample Data View** – Table listing sample fake and real article titles for quick inspection.
---

🧮 DAX Calculations Used
```DAX
Total News = COUNTROWS('FakeNews')

Fake News Count = CALCULATE(
    COUNTROWS('FakeNews'),
    'FakeNews'[label] = "Fake"
)

Real News Count = CALCULATE(
    COUNTROWS('FakeNews'),
    'FakeNews'[label] = "Real"
)

Fake News % = DIVIDE([Fake News Count], [Total News], 0) * 100

```

---

📂 Dataset Information
The dataset contains labeled news articles from various sources and categories.
Each article is classified as **Fake** or **Real** based on the `label` column.

---

🎯 Purpose
The primary goal of this dashboard is to:
* Monitor fake news trends over time.
* Identify sources with higher fake news occurrences.
* Support data-driven decisions to combat misinformation.

---

⚙️ Tools & Technologies
* **Power BI** for data visualization
* **DAX** for metric calculations
* **Excel/CSV** as data source

---
📌 Insights
* Approximately **50.28%** of articles in the dataset are fake.
* Fake news peaked in **2023 and 2024**, then dropped sharply in 2025.
* Fake news is evenly distributed across most categories and sources, with "Not Known" being the lowest contributor.
