# 📊 Fraud Detection Model Performance Analysis

This project investigates the declining accuracy of London's **Poundbank fraud detection model**.  
It uses the **nannyml** library to analyze data drift and model performance degradation, culminating in an interactive single-page web application to present the findings.

---

## 📑 Table of Contents
- [Project Overview](#project-overview)
- [Key Findings](#key-findings)
- [Interactive Web Application](#interactive-web-application)
- [Technical Stack](#technical-stack)
- [How to Run the Analysis](#how-to-run-the-analysis)
- [Recommendations](#recommendations)

---

## 1. Project Overview

Banks are in a continuous battle against evolving fraud tactics.  
Machine learning models, while powerful, can become less effective when the underlying data patterns shift—a phenomenon known as **data drift**.

This repository contains the analysis and findings for a fraud detection model that has begun to underperform in a production environment.  

The core objectives were to:
- Pinpoint the exact months when the model's performance began to degrade.  
- Identify which feature's data drift is most correlated with this performance drop.  
- Provide a clear, actionable report for stakeholders.  

✅ The result is a **self-contained analysis notebook** and a **single-page interactive web application** that makes the complex findings easy to explore and understand for both technical and business audiences.

---

## 2. Key Findings

- ⚠️ **Performance Alerts Triggered**: The model's accuracy dropped significantly and triggered alerts during **April, May, and June of 2019**.  
- 🎯 **Root Cause**: The primary reason for the performance decline is **data drift**. Fraudsters have changed their tactics, making them harder to detect by the current model.  
- 🔑 **Highest Correlating Feature**: `time_since_login_min` – fraudulent transactions are no longer occurring immediately after a user logs in, a key pattern the original model relied on.  
- 📈 **Secondary Indicator**: An increase in the average `transaction_amount` also contributed, as fraudsters began making larger, less frequent transfers.

---

## 3. Interactive Web Application

The core of this project is the **single-page interactive web application (`index.html`)** that translates the data analysis into a consumable, visual story.  

The application allows users to:
- 📉 **Explore Performance Trends**: A line chart visualizes the model's accuracy over time, showing a clear drop during the alert periods.  
- 🕵️ **Identify the Root Cause**: A bar chart ranks features by correlation with performance drop, highlighting `time_since_login_min` as the main issue.  
- 📖 **Understand the Narrative**: The application guides the user through findings with explanatory text, making the data accessible to non-technical stakeholders.  

---

## 4. Technical Stack

| Component       | Technology                  | Purpose |
|-----------------|-----------------------------|---------|
| Data Analysis   | Python, `nannyml`, `pandas` | Analyzing model performance, data drift, and correlations |
| Web Application | HTML, CSS (Tailwind CDN)    | Building the responsive single-page application |
| Visualization   | JavaScript, Chart.js (CDN)  | Interactive line and bar charts |
| Interactivity   | Vanilla JavaScript          | Navigation, filtering, and chart updates |

---

## 5. How to Run the Analysis

1. **Clone the repository** and download the datasets. Ensure `reference.csv` and `analysis.csv` are in the same directory as your Python script.  

2. **Install dependencies**:
   ```bash
   pip install nannyml pandas


## 6. Recommendations

🔄 Model Retraining: Retrain the model with a dataset reflecting new fraudulent behaviors.

🛡️ Continuous Monitoring: Implement permanent monitoring of data drift for proactive detection.

🔍 Further Investigation: Study new fraud tactics (changes in time_since_login_min and transaction_amount) for deeper insights.

