# 🏥 HealthConnect Appointment Analytics

## 📌 Project Overview

**HealthConnect Clinic** is a fictional healthcare provider experiencing challenges related to missed appointments, appointment-slot utilisation, and patient engagement.

As part of the **AnalystLab Africa Experience Lab – Week 4 Data Analytics Track**, I analysed the HealthConnect appointment dataset to understand appointment attendance and identify patterns associated with missed appointments.

<img width="1390" height="776" alt="Screenshot 2026-08-30 134847" src="https://github.com/user-attachments/assets/53332fee-f1b1-4b14-bd80-f36b8d0378d2" />



### 🎯 Central Project Question

> **How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?**

---

## 🎯 Project Objectives

The objectives of this analysis were to:

- Understand the HealthConnect appointment dataset.
- Assess the quality and completeness of the data.
- Identify variables relevant to appointment attendance.
- Investigate appointment outcome patterns.
- Define meaningful business questions.
- Identify relevant KPIs.
- Establish an analytical approach for the next phase of the project.

---
# 📅 Project Journey

## 🔹 Week 4 — Project Foundation

Week 4 focused on establishing the foundation for the HealthConnect analytics project.
## 🗂️ Dataset

---
The dataset contains **5,000 appointment records** and **18 variables** relating to:

- 👤 Patient demographics
- 📅 Appointment details
- 📝 Booking information
- 🔄 Previous appointment history
- ❌ Previous no-shows
- 📲 Reminder information
- 📍 Distance to the clinic
- ⏳ Waiting time
- 📊 Appointment outcomes

### Appointment Outcomes

The appointment outcome categories are:

- ✅ Attended
- ❌ No-Show
- 🚫 Cancelled

---

## 🔍 Data Quality Assessment

The initial data-quality assessment identified:

| Data Quality Check | Result |
|---|---:|
| Total Records | 5,000 |
| Total Variables | 18 |
| Exact Duplicate Rows | 0 |
| Duplicate Appointment IDs | 0 |
| Missing Distance Values | 90 (1.8%) |
| Missing Waiting-Time Values | 60 (1.2%) |
| Invalid Negative Booking Lead Days | 0 |
| Previous No-Shows > Previous Appointments | 0 |
| Booking Date Later Than Appointment Date | 0 |

Additional validation confirmed that **booking lead days were consistent with the booking and appointment dates**.

The original dataset was preserved, and analysis was conducted using the working analysis file.

---

## 📊 Key Findings

### 1. Appointment Outcomes

| Outcome | Appointments | Rate |
|---|---:|---:|
| ❌ No-Show | 2,423 | 48.5% |
| ✅ Attended | 2,314 | 46.3% |
| 🚫 Cancelled | 263 | 5.3% |
| **Total** | **5,000** | **100%** |

The analysis shows that **No-Show was the largest appointment outcome category**, representing **48.5%** of all appointments.

This indicates a significant opportunity for HealthConnect to improve appointment attendance and patient engagement.

---

### 2. Previous No-Shows

Appointments with at least one previous no-show had a higher observed current no-show rate than appointments with no previous no-shows.

| Previous No-Shows | Current No-Show Rate |
|---|---:|
| 0 previous no-shows | 43.5% |
| At least 1 previous no-show | 55.8% |

This suggests that **previous appointment behaviour may be useful when identifying patients who could benefit from additional appointment support**.

> ⚠️ These findings represent descriptive associations and should not be interpreted as proof of causation.

---

### 3. Booking Lead Time

A relationship was also observed between booking lead time and no-show rate.

| Booking Lead Time | No-Show Rate |
|---|---:|
| 1–7 days | 27.8% |
| 46–60 days | 67.7% |

The observed pattern suggests that appointments booked further in advance may require additional engagement or reminder strategies.

> ⚠️ These findings are descriptive associations and do not establish causation.

---

## 📈 Proposed KPIs

The following KPIs were identified for the HealthConnect project:

| KPI | Purpose |
|---|---|
| **No-Show Rate** | Measures the percentage of appointments that patients miss |
| **Attendance Rate** | Measures the percentage of appointments attended |
| **Cancellation Rate** | Measures the percentage of appointments cancelled |
| **Reminder Coverage Rate** | Measures the percentage of appointments receiving reminders |
| **Average Booking Lead Time** | Measures the average number of days between booking and appointment |

These KPIs will support deeper analysis and decision-making in subsequent project stages.

---

## 💡 Business Questions

The analysis was designed around questions such as:

1. What percentage of appointments are missed?
2. Which patient groups have higher no-show rates?
3. Does previous no-show behaviour relate to future attendance?
4. Does booking lead time affect appointment attendance?
5. Does receiving a reminder relate to attendance?
6. Does distance from the clinic influence no-show behaviour?
7. Which appointment characteristics are associated with higher no-show rates?
8. How can HealthConnect use these insights to improve patient engagement?

---
## 🔹 Week 5 — Data Analysis and Insights

Week 5 builds directly on the analytical foundation established in Week 4.

The project progressed from planning into practical data analysis.

### Activities Completed

- Data preparation.
- Data quality assessment.
- Exploratory Data Analysis (EDA).
- Appointment attendance analysis.
- No-show analysis.
- KPI development.
- Data visualisation.
- Dashboard development.
- Business insight generation.
- Recommendation development.

---

# 📊 Project Dashboard

<img width="5960" height="6127" alt="healthconnect_chart (1)" src="https://github.com/user-attachments/assets/45653405-7e51-40c9-bd24-fb2f9636bc11" />


The dashboard provides an overview of appointment performance and highlights the key factors associated with missed appointments.

---

# 🛠️ Tools and Technologies

The following tools and technologies were used throughout the project:

- Python
- Pandas
- Matplotlib
- Jupyter Notebook
- Microsoft Excel
- GitHub

---

# 📂 Dataset

The HealthConnect appointment dataset contains **5,000 appointment records**.

The dataset includes information relating to:

- Appointment ID
- Patient demographics
- Appointment type
- Appointment day
- Appointment outcome
- Booking lead time
- Distance to clinic
- Previous appointments
- Previous no-shows
- Reminder status
- Reminder channel
- Waiting time

---

# 🧹 Data Preparation

Building on the Week 4 data understanding phase, Week 5 focused on validating and preparing the dataset for analysis.

The data preparation process included:

- Checking data types.
- Checking for missing values.
- Checking for duplicate records.
- Validating appointment IDs.
- Checking logical consistency.
- Reviewing categorical values.
- Reviewing numerical ranges.

The dataset was then prepared for exploratory data analysis.

---

# 📈 Exploratory Data Analysis

## 1️⃣ Overall Appointment Attendance

<img width="1468" height="1270" alt="appointment distribution" src="https://github.com/user-attachments/assets/07821e5b-a0af-446b-ab9c-6d90982a7a70" />


The first stage of the analysis examined the overall appointment outcome distribution.

### Key Finding

- **48.5%** of appointments resulted in a No-Show.
- **46.3%** of appointments were attended.
- **5.3%** of appointments were cancelled.

Missed appointments were identified as HealthConnect's primary attendance challenge.

---

## 2️⃣ No-Shows by Booking Lead Time

<img width="2060" height="1310" alt="no_shows_by_booking_time_" src="https://github.com/user-attachments/assets/829dde67-29d4-41ec-9fb6-eae2dca459c9" />

Booking lead time was identified as one of the strongest factors associated with missed appointments.

The no-show rate increased from **24.8% for appointments booked 0–3 days ahead** to **60.5% for appointments booked 31–60 days ahead**.

### Key Insight

Appointments scheduled far in advance were more likely to result in missed appointments.

---

## 3️⃣ No-Shows by Distance to Clinic

<img width="2060" height="1310" alt="no_shows_by_distance_to_clinic" src="https://github.com/user-attachments/assets/dd7202db-73af-448c-9ebb-868d6dc70686" />

The analysis explored the relationship between patient distance and appointment attendance.

### Key Finding

Patients living farther from the clinic showed higher no-show rates.

The no-show rate increased from:

- **46.5% for patients within 5km**
- To **68.1% for patients living 30–50km away**

### Key Insight

Distance and accessibility may contribute to missed appointments.

---

## 4️⃣ Previous No-Show History

<img width="2060" height="1310" alt="no_shows_by_previous_no_shows" src="https://github.com/user-attachments/assets/d0ac8178-2d13-499b-8ca3-76911e8821c2" />

Previous attendance behaviour showed a strong relationship with future appointment attendance.

### Key Finding

Patients with **3 or more previous no-shows** had a **68.8% no-show rate**, compared with **43.5% for patients with no previous no-shows**.

### Key Insight

Previous attendance history can help identify patients who may require additional follow-up and support.

---

## 5️⃣ Appointment Reminder Analysis

<img width="2960" height="1311" alt="no_shows_by_reminder" src="https://github.com/user-attachments/assets/4f3bf2ad-bfa4-4832-98e1-93362462261a" />

The analysis also examined whether appointment reminders influenced attendance.

### Key Findings

- No-show rate without reminders: **51.4%**
- No-show rate with reminders: **47.4%**
- Best-performing reminder channel: **SMS at 45.8%**

### Key Insight

Appointment reminders showed a modest improvement in attendance, with SMS performing better than other reminder channels.

---

# 📊 Key Performance Indicators

| KPI | Result |
|-----|--------|
| Total Appointments | 5,000 |
| Attendance Rate | 46.28% |
| No-Show Rate | 48.46% |
| Cancellation Rate | 5.26% |
| No-Show Rate Among Non-Cancelled Appointments | 51.15% |

---

# 💡 Key Business Insights

### 🔴 Missed Appointments Are the Main Challenge

No-Shows represent the largest appointment outcome and slightly exceed attended appointments.

### ⏳ Booking Lead Time Is a Major Driver

Appointments booked far in advance showed significantly higher no-show rates.

### 📍 Distance Affects Attendance

Patients living farther from the clinic were more likely to miss appointments.

### 🔄 Previous Behaviour Predicts Future Behaviour

Patients with a history of missed appointments showed a higher likelihood of future no-shows.

### 📱 Reminders Help Improve Attendance

Appointment reminders reduced no-show rates, with SMS showing the strongest performance.

---

# 💼 Recommendations

## 1. Prioritise SMS Reminders

Use SMS as the primary reminder channel while evaluating other communication channels as secondary options.

## 2. Support High-Risk Patients

Provide proactive reminders and follow-up for patients with a history of missed appointments.

## 3. Monitor Long Lead-Time Appointments

Introduce additional reminder strategies for appointments booked far in advance.

## 4. Address Distance and Access Barriers

Explore suitable support options for patients living farther from the clinic.

## 5. Monitor Appointment Performance

Continuously track attendance and no-show KPIs to measure improvement.

---

# 🚀 Skills Demonstrated

Throughout Week 4 and Week 5, this project demonstrates the following skills:

- Data Understanding
- Data Cleaning and Preparation
- Data Quality Assessment
- Exploratory Data Analysis
- Data Visualisation
- KPI Development
- Business Analysis
- Healthcare Data Analysis
- Python
- Pandas
- Matplotlib
- GitHub Documentation
- Business Insight Generation

---

# 📁 Project Structure

```text
HealthConnect-Appointment-Analytics/
│
├── README.md
│
├── data/
│   └── HealthConnect_Appointment_Data.csv
│
├── notebooks/
│   ├── Week4_HealthConnect_Analysis.ipynb
│   └── Week5_HealthConnect_Analysis.ipynb
│
├── images/
│   ├── appointment_outcome.png
│   ├── booking_lead_time.png
│   ├── distance_to_clinic.png
│   ├── previous_no_shows.png
│   ├── reminder_analysis.png
│   └── healthconnect_dashboard.png
│
├── reports/
│   ├── Week4_Report.pdf
│   └── HealthConnect_Week5_Data_Analytics_Report.pdf
│
└── README.md
📈 Project Progress
Week	Focus	Status
Week 4	Project Foundation and Planning	✅ Completed
Week 5	Data Analysis and Insights	✅ Completed
Week 6	Further Project Development	🔄 Upcoming
⚠️ Project Limitations
The dataset is fictional/synthetic.
The analysis identifies patterns and associations rather than causation.
Some fields contain small amounts of missing information.
Cancelled appointments were analysed separately from No-Shows.
👩‍💻 Author

Tejumade Adeyinka

Data Analyst

Skills

Python | Excel | SQL | Power BI | Data Analysis | Data Visualisation

⭐ Project Status

Week 5 Completed

This project is an ongoing HealthConnect analytics project. Week 5 builds directly on the Week 4 foundation, with future project phases expected to expand the analysis and develop additional stakeholder-focused solutions.


