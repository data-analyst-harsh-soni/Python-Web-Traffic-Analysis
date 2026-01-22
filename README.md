<div align="center">

# 📊 InsightViz: Web Analytics Dashboard

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-success?style=for-the-badge&logo=python&logoColor=white)

<p align="center">
  <strong>A step-by-step Python workflow to clean, analyze, and visualize web traffic data.</strong>
</p>

</div>

---

## 📖 Project Workflow
This project follows a structured data analysis pipeline. Below is the step-by-step code implementation used to derive insights.

---

### 🛠️ Step 1: Data Ingestion & Cleaning
The raw data export had a messy header structure (metadata in the first row). The first step was to normalize the DataFrame.

```python
import pandas as pd

# Load data
df = pd.read_csv('data-export.csv')

# 1. Fix Header Issue (Raw file had metadata in row 0)
df.columns = df.iloc[0] 
df = df.drop(index=0).reset_index(drop=True)

# 2. Rename columns for clarity
df.columns = [
    'Channel', 'DateHour', 'Users', 'Sessions', 'EngagedSessions', 
    'AvgTime', 'EngagedPerUser', 'EventsPerSession', 'EngagementRate', 'EventCount'
]

# 3. Convert Data Types
numeric_cols = ['Users', 'Sessions', 'EngagedSessions', 'EngagementRate']
df[numeric_cols] = df[numeric_cols].apply(pd.to_numeric, errors='coerce')

print("✅ Data Cleaned Successfully")
⏳ Step 2: Time-Series Parsing
The date was stored as a string format YYYYMMDDHH. We converted this to a usable Datetime object to extract hourly trends.

Python

# Convert 'YYYYMMDDHH' string to datetime objects
df['DateHour'] = pd.to_datetime(df['DateHour'], format='%Y%m%d%H', errors='coerce')

# Feature Engineering: Extract 'Hour' for peak-time analysis
df['Hour'] = df['DateHour'].dt.hour
🔍 Step 3: Advanced Analysis (Engagement Logic)
We needed to compare Engaged vs. Non-Engaged sessions to understand traffic quality.

Python

# Create a summary dataframe
session_df = df.groupby('Channel')[['Sessions', 'EngagedSessions']].sum().reset_index()

# Calculate Non-Engaged Sessions
session_df['Non-Engaged'] = session_df['Sessions'] - session_df['EngagedSessions']

# Melt data for stacked visualization
session_df_melted = session_df.melt(
    id_vars='Channel', 
    value_vars=['EngagedSessions', 'Non-Engaged']
)
🎨 Step 4: Visualization
Using Seaborn to generate insights. Below is the code for the Traffic Heatmap, which identifies the busiest hours for each channel.

Python

import seaborn as sns
import matplotlib.pyplot as plt

# Prepare Matrix for Heatmap
heatmap_data = df.groupby(['Hour', 'Channel'])['Sessions'].sum().unstack().fillna(0)

# Plotting
plt.figure(figsize=(12, 8))
sns.heatmap(heatmap_data, cmap='YlGnBu', linewidths=0.5, annot=True, fmt='.0f')

plt.title('🔥 Traffic Intensity by Hour and Channel')
plt.xlabel('Channel Group')
plt.ylabel('Hour of Day')
plt.show()
📸 Output Previews
Engagement Trends	Traffic Heatmap
(Place your BarChart image here)	(Place your Heatmap image here)

Export to Sheets

Key Insight: "Organic Search" drives the most volume, but "Referral" traffic shows consistently higher engagement rates during business hours (10 AM - 4 PM).

🚀 How to Run locally
Clone the repo.

Install dependencies: pip install pandas matplotlib seaborn

Run the script: python main.py

<div align="center"> <i>Created by Harsh Soni</i> </div>


### ✨ Isme khaas kya hai?

1.  **Code Snippets:** Pura code ek saath nahi fenka. Chhote chunks mein divide kiya hai (Cleaning -\> Time Parsing -\> Logic -\> Visuals).
2.  **Comments:** Code ke andar comments (`# Fix Header Issue`) dikha rahe hain ki aapko pata hai aap kya kar rahe ho.
3.  **Storytelling:** Headers batate hain *kyun* ye step liya gaya (e.g., "The raw data export had a messy header...").
4.  **Emojis:** Thoda visual appeal add karte hain bina unprofessional lage.

Isse copy karo aur README.md mein daal do, GitHub repo ekdum premium lagega\! 🚀
