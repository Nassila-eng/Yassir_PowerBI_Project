# Yassir_PowerBI_Project
Power BI dashboard analyzing Yassir business performance (fictional dataset)
# 🚗 Power BI Project – Yassir Business Performance Dashboard

## 📊 Project Overview
This project presents a **Power BI dashboard** that analyzes the performance of a fictional company inspired by **Yassir**, a popular ride-hailing and delivery platform operating in North Africa.  
The dashboard provides insights into **ride services**, **delivery operations**, **drivers' performance**, **customer feedback**, and **financial results**.

The objective is to simulate a real-world **data analysis case** and demonstrate practical skills in **data modeling, DAX calculations, and interactive visualization** using Power BI.

---

## 🎯 Objectives
- Visualize the company’s overall performance using key metrics (KPIs).  
- Analyze **drivers’ acceptance and cancellation rates**.  
- Evaluate **customer satisfaction** based on delivery and ride metrics.  
- Track **financial efficiency** through expense/revenue ratios and profit margins.  
- Identify **trends and opportunities** to optimize services.

---

## 🧩 Dataset Description
The dataset was synthetically generated to simulate Yassir’s business data and contains six main tables:

| Table Name | Description |
|-------------|--------------|
| **Course** | Ride service data (duration, distance, price, rating, date) |
| **Livraison** | Delivery operations including delivery time, distance, satisfaction score |
| **Chauffeur-Livreur** | Driver details (type, city, acceptance/cancellation rate, averages) |
| **Client** | Customer profiles and types (ride, delivery, both) |
| **Feedback** | Customer feedback including type (complaint/compliment), comments, and dates |
| **Finance** | Financial data by service and date (revenues, expenses) |

---

## ⚙️ Data Model
All tables were imported from Excel into Power BI and linked using key relationships such as:
- **Driver ID**, **Client ID**, **Transaction ID**, and **Date**.

The model allows cross-table analysis between operational, financial, and customer dimensions.

*(Optional: insert a screenshot of your data model if available)*

---

## 💡 Key Measures (DAX)

### 🔹 Revenue KPIs
```DAX
Total Revenues = SUM('Finance'[Revenus])

Previous Revenues = 
CALCULATE(
    SUM('Finance'[Revenus]),
    DATEADD('Finance'[Date], -1, MONTH)
)

Growth Rate (%) = 
DIVIDE(([Total Revenues] - [Previous Revenues]), [Previous Revenues], 0)
