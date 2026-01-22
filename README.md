# 📊 InsightViz: Web Traffic Analyzer



![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)

![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)

![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-success?style=for-the-badge&logo=python&logoColor=white)



<p align="center">

  <strong>Transforming raw web analytics data into actionable user behavior insights.</strong>

</p>



</div>



---



## 📌 Project Overview



**InsightViz** is a Python-based data cleaning and visualization dashboard designed to analyze web traffic trends. 



Raw web analytics data is often messy and hard to interpret. This project automates the process of **cleaning, formatting, and visualizing** that data to answer key questions about user engagement, peak traffic times, and channel performance.



---



## 🚀 Key Features



* **🧹 Data Cleaning Pipeline:** Automated handling of missing values and formatting of messy columns (like specific `Date-Hour` formats).

* **🕒 Time-Series Analysis:** Parsing string timestamps into usable Datetime objects for trend analysis.

* **🔥 Advanced Visualization:** Uses **Matplotlib** and **Seaborn** to generate:

    * Traffic Heatmaps (Hour vs. Channel)

    * Engagement Rate Boxplots

    * User Growth Trends over time



---



## 📸 Visualization Preview



*(Place your actual graph screenshots here. For now, here is a description of the outputs)*



| Visual Type | Purpose |

| :--- | :--- |

| **📈 Time Series** | Tracks User and Session growth over the selected period. |

| **🔥 Heatmap** | Identifies the "Hottest" hours for traffic across different channels. |

| **📊 Boxplot** | Analyzes the spread of Engagement Rates to detect outliers. |

| **📉 Bar Charts** | Compares User distribution across Organic Search, Social, and Direct channels. |



---



## 🛠️ Tech Stack



<div align="center">

  <img src="https://img.shields.io/badge/Language-Python-blue?style=flat-square" />

  <img src="https://img.shields.io/badge/Library-Pandas-150458?style=flat-square" />

  <img src="https://img.shields.io/badge/Library-NumPy-013243?style=flat-square" />

  <img src="https://img.shields.io/badge/Library-Matplotlib-black?style=flat-square" />

  <img src="https://img.shields.io/badge/Library-Seaborn-7db954?style=flat-square" />

</div>



---



## 📂 Dataset Details



The script processes a raw CSV export (`data-export (1).csv`) containing the following key metrics:

* **Dimensions:** Channel Group, Date + Hour info.

* **Metrics:** Active Users, Sessions, Event Counts.

* **Engagement:** Engagement Rate, Average Engagement Time.



> *Note: The dataset used is a sample export mimicking Google Analytics 4 (GA4) raw data structures.*



---



## 📦 How to Run This Project



1.  **Clone the Repository**

    ```bash

    git clone [https://github.com/data-analyst-harsh-soni/InsightViz-Web-Traffic.git](https://github.com/data-analyst-harsh-soni/InsightViz-Web-Traffic.git)

    ```



2.  **Install Dependencies**

    Ensure you have the required libraries installed:

    ```bash

    pip install pandas numpy matplotlib seaborn

    ```



3.  **Run the Analysis Script**

    ```bash

    python main.py

    ```

    *(The charts will generate and display automatically)*



---



## 🧠 Key Insights (Sample)



* **Peak Traffic:** Analysis revealed that "Organic Search" brings in the most users, but "Referral" traffic has a higher engagement rate.

* **Time Trends:** User activity peaks between **10:00 AM and 2:00 PM**, suggesting the best time for content updates.

* **Engagement:** A clear correlation was found between "Session Duration" and "Conversion Events."



---



## 👤 Author



**Harsh Soni**

*Aspiring Data Analyst | Python & SQL Enthusiast*



[LinkedIn](https://www.linkedin.com/in/harsh-soni-data-analyst) | [GitHub Profile](https://github.com/data-analyst-harsh-soni)



---



⭐ **If you found this analysis helpful, please star the repo!**
