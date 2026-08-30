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

## 🗂️ Dataset

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

## 🛠️ Tools & Technologies

The project used:

- 🟢 **Microsoft Excel**
- 📊 **Exploratory Data Analysis**
- 🧹 **Data Quality Assessment**
- 📈 **Data Analysis**
- 💡 **Business Intelligence**
- 🤖 **Analytical Thinking**

---

## 🔄 Analytical Approach

The project followed a structured analytical process:

```text
Raw Dataset
     ↓
Data Quality Assessment
     ↓
Data Validation
     ↓
Exploratory Data Analysis
     ↓
Identify Patterns
     ↓
Define KPIs
     ↓
Generate Business Questions
     ↓
Develop Insights
     ↓
AI & Predictive Analytics Opportunities
