# HealthConnect Clinic — Appointment Analytics & Decision Support

### AnalystLab Africa Experience Lab · Data Analytics & Data Science Tracks

<img width="800" alt="HealthConnect project overview" src="https://github.com/user-attachments/assets/53332fee-f1b1-4b14-bd80-f36b8d0378d2" />

**Project question:** How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?

HealthConnect Clinic is a fictional healthcare provider used as the basis for an eight-week, multidisciplinary project within the AnalystLab Africa Experience Lab. This repository documents the Data Analytics track's contribution — from initial data understanding through to a tested, validated, and presentation-ready final solution — and its collaboration with the project's Data Science track.

---

## Contents

- [Project Objectives](#project-objectives)
- [Dataset](#dataset)
- [Data Quality Assessment](#data-quality-assessment)
- [Project Journey](#project-journey)
- [Final Key Performance Indicators](#final-key-performance-indicators)
- [Final Business Insights & Recommendations](#final-business-insights--recommendations)
- [Cross-Track Collaboration](#cross-track-collaboration)
- [Repository Structure](#repository-structure)
- [How to Run](#how-to-run)
- [Limitations](#limitations)
- [Tools & Skills Demonstrated](#tools--skills-demonstrated)

---

## Project Objectives

- Understand the HealthConnect appointment dataset and assess its quality and completeness.
- Identify the variables and patterns most closely associated with missed appointments.
- Develop KPIs and a decision-support dashboard for clinic stakeholders.
- Statistically validate the identified drivers and build a reproducible patient risk score.
- Test, refine, and cross-validate the analysis against an independently built predictive model.
- Deliver a final, presentation-ready package supporting HealthConnect's operational decisions.

---

## Dataset

The dataset contains **5,000 appointment records** across **18 variables**, covering:

- Patient demographics (age, gender)
- Appointment details (type, day, outcome)
- Booking information (lead time, appointment ID)
- Prior appointment history and prior no-shows
- Reminder information (sent status, channel)
- Distance to clinic and waiting time

**Appointment outcomes:** Attended · No-Show · Cancelled

---

## Data Quality Assessment

| Check | Result |
|---|---:|
| Total records | 5,000 |
| Total variables | 18 |
| Exact duplicate rows | 0 |
| Duplicate appointment IDs | 0 |
| Missing distance values | 90 (1.8%) |
| Missing waiting-time values | 60 (1.2%) |
| Invalid negative booking lead days | 0 |
| Previous no-shows exceeding previous appointments | 0 |
| Booking date later than appointment date | 0 |

Booking lead days were independently verified against the booking and appointment dates for consistency. The original dataset file was never modified — all analysis was performed on working copies, with derived fields and segments computed separately.

---

## Project Journey

### Week 4 — Project Foundation

Established the analytical foundation for the project: reviewed the dataset structure, ran the initial data-quality assessment above, defined the central project question, and identified an initial set of candidate KPIs and business questions to guide the analysis (missed-appointment rate, attendance patterns by patient group, the influence of booking lead time, distance, and reminders on attendance).

### Week 5 — Exploratory Data Analysis & Initial Dashboard

Moved from planning into practical analysis: data preparation, exploratory data analysis, KPI development, dashboard construction, and an initial set of business recommendations.

<img width="500" alt="Appointment outcome distribution" src="https://github.com/user-attachments/assets/07821e5b-a0af-446b-ab9c-6d90982a7a70" />

**Overall attendance.** No-Show was the largest single outcome category — **48.5%** of appointments — ahead of Attended (46.3%) and Cancelled (5.3%).

<img width="600" alt="No-shows by booking lead time" src="https://github.com/user-attachments/assets/829dde67-29d4-41ec-9fb6-eae2dca459c9" />

**Booking lead time.** No-show rate rose from **24.8%** for appointments booked 0–3 days ahead to **67.7%** for appointments booked 46–60 days ahead — one of the strongest patterns in the dataset.

<img width="600" alt="No-shows by distance to clinic" src="https://github.com/user-attachments/assets/dd7202db-73af-448c-9ebb-868d6dc70686" />

**Distance to clinic.** No-show rate rose from **46.5%** for patients within 5 km to **68.1%** for patients 30–50 km away.

<img width="600" alt="No-shows by previous no-show history" src="https://github.com/user-attachments/assets/d0ac8178-2d13-499b-8ca3-76911e8821c2" />

**Prior no-show history.** Patients with three or more previous no-shows had a **68.8%** current no-show rate, compared with **43.5%** for patients with no prior no-shows.

<img width="700" alt="No-shows by reminder channel" src="https://github.com/user-attachments/assets/4f3bf2ad-bfa4-4832-98e1-93362462261a" />

**Reminders.** No-show rate was **51.4%** without a reminder versus **47.4%** with one; SMS was the best-performing individual channel at **45.8%**.

These Week 5 findings were descriptive and associational, and were explicitly flagged as not establishing causation — a distinction the project carried forward and later tested statistically in Week 6.

### Week 6 — Statistical Validation & Risk Segmentation

Built directly on Week 5 rather than repeating it: moved from descriptive, bucketed rates to statistically validated, jointly modelled drivers, and from a single-variable risk flag to a compound risk score.

- **Statistical validation.** Chi-square tests and a joint logistic regression confirmed that booking lead time, distance, prior no-shows, and reminder status are each independently significant drivers of no-shows (p < 0.05), even after controlling for one another. Waiting time and appointment day were confirmed as non-drivers.
- **Compound risk segmentation.** A new 0–3 risk score (+1 point each for lead time > 14 days, distance > 10 km, and prior no-shows ≥ 1) produced a clean, monotonic no-show gradient from 24.6% to 65.1%, and captured **62.9% of all no-shows within 54.4% of appointments** — versus just 13.4% captured by the Week 5 single-variable rule.
- **Reminder-by-risk-tier test.** No meaningful difference in reminder effectiveness was found across risk tiers, suggesting reminders should stay universal, with the risk score instead used to target additional, non-reminder follow-up.
- **Cross-track integration.** The validated risk score and feature set were shared with the Data Science track as a benchmark for their predictive model, with the dependency documented in both directions.

<img width="900" alt="HealthConnect analytics dashboard" src="https://github.com/user-attachments/assets/45653405-7e51-40c9-bd24-fb2f9636bc11" />

### Week 7 — Testing, Refinement & End-to-End Validation

Rather than assuming the Week 6 outputs were correct, Week 7 re-tested every reported figure against the underlying data.

- **KPI correction.** The Week 6 report's headline "risk score ≥2" no-show rate (59.0%) turned out to be an unweighted average of two tier-level rates rather than the correct, n-weighted pooled rate. The corrected figure is **56.0%**; every other Week 6 figure reproduced exactly.
- **Segment stability.** The risk-score gradient was confirmed to hold across gender, age group, and appointment type (12 of 13 segments tested).
- **Statistical power.** Week 6's under-powered, split-sample reminder test was replaced with a single pooled interaction model on the full dataset — the "reminder effect does not vary by risk tier" finding was upgraded from suggestive to **confirmed** (p = 0.732).
- **Data-quality audit.** No duplicates, no invalid ranges, and all missing values were traced to an explainable cause.
- **Cross-track validation (interim).** The rule-based risk score was compared against a model-based probability estimate, using an interim in-house logistic model as a stand-in while Data Science's own Week 6 model output was still pending (r = 0.658, directionally consistent).

### Week 8 — Final Integration & Presentation

Finalised the Data Analytics track's contribution into a decision-ready package and closed out the cross-track validation with real data from the Data Science track.

- **Cross-track dependency closed.** Data Science's actual refined model (a regularized logistic regression) was compared against the Data Analytics risk score on a proper held-out test set: AUC 0.596 (rule-based) vs. 0.662 (model-based), correlation r = 0.642. This also surfaced a genuine methodological finding — the original in-sample comparison in this project had overstated both AUC figures (0.609 / 0.680) — which is now corrected in both tracks' final numbers.
- **Final package delivered:** a final notebook reproducing every headline figure from the raw dataset, a business-facing report (executive summary, final KPIs, recommendations, and the closed HC-POD integration record), a presentation deck, and an individual video script for the final HC-POD walkthrough.

---

## Final Key Performance Indicators

| KPI | Value |
|---|---:|
| Total appointments analysed | 5,000 |
| Overall no-show rate | 48.5% |
| Attendance rate | 46.3% |
| Cancellation rate | 5.3% |
| No-show rate — risk score 0–1 (not flagged) | 39.4% |
| No-show rate — risk score ≥2 (flagged) | 56.0% |
| Share of appointments flagged by the risk score | 54.4% |
| Share of all no-shows captured by the flagged segment | 62.9% |
| No-show rate — reminder sent | 47.4% |
| No-show rate — no reminder sent | 51.4% |
| Cross-track benchmark — rule-based score (held-out AUC) | 0.596 |
| Cross-track benchmark — Data Science's model (held-out AUC) | 0.662 |

---

## Final Business Insights & Recommendations

**Validated insights**

1. Booking lead time, distance to clinic, and prior no-show history are statistically confirmed, independent drivers of missed appointments — not merely descriptive patterns.
2. Waiting time and appointment day are confirmed **not** to be drivers, across every testing round in both the Data Analytics and Data Science tracks.
3. The compound risk score (0–3) is validated and stable across patient segments, and its headline KPI has been corrected and independently reproduced.
4. Reminder effectiveness does not vary meaningfully by risk tier — reminders should remain universal rather than targeted.
5. Data Science's predictive model adds a genuine, if modest, improvement over the rule-based score (held-out AUC 0.662 vs. 0.596) and is best used as a complementary layer, not a replacement.

**Recommendations**

1. Deploy the 0–3 risk score as the primary triage tool for administrative follow-up: light-touch for scores 0–1, proactive outreach for score 2, and priority phone-call or rescheduling support for score 3.
2. Keep SMS reminders universal across all patients, regardless of risk tier.
3. As ML Engineering integrates Data Science's model into an operational pipeline, treat it as a secondary refinement layer on top of the interpretable rule-based score, not an immediate replacement.
4. Track no-show rate, capture rate by risk tier, and reminder compliance as ongoing KPIs.
5. Design and run a properly powered, stratified reminder-timing/channel test as the next analytical investment.

---

## Cross-Track Collaboration

| | Provided to Data Science | Received from Data Science |
|---|---|---|
| Week 6 | Validated features and compound risk score, as a benchmark for their baseline model | Confirmation of baseline model features used |
| Week 7 | Corrected KPI, properly powered reminder finding, interim AUC/correlation benchmark | — (Week 6 model output still pending) |
| Week 8 | Final validated risk score and driver list | Final refined model, held-out AUC benchmark, and an in-sample-vs-held-out methodological correction — **dependency closed** |

**Open dependencies going into final integration:**
- ML Engineering — feature list, preprocessing steps, and model coefficients for pipeline integration.
- Project Management — a decision-threshold review, since Data Science's error analysis found false negatives more frequent than false positives.

---

## Repository Structure

```
├── data/
│   └── HealthConnect_Appointment_Data.csv                     # approved project dataset (not modified)
├── notebooks/
│   ├── week_7_healthconnect.ipynb                             # testing, refinement, cross-track validation
│   └── week_8_healthconnect.ipynb                             # final KPIs, dashboard, business insights
├── reports/
│   ├── HealthConnect_Week6_Data_Analytics_Report.pdf
│   ├── HealthConnect_Week6_Project_Summary.pdf
│   ├── HealthConnect_Week7_Data_Analytics_Testing_Report.docx
│   ├── HealthConnect_Week7_Project_Summary.docx
│   └── HealthConnect_Week8_Data_Analytics_Final_Package.pdf
├── presentation/
│   ├── HealthConnect_Week8_Data_Analytics_Presentation.pptx
│   └── HealthConnect_Week8_Video_Script_Data_Analytics.docx
└── README.md
```
*(Adjust the layout above to match your repository's actual organisation.)*

---

## How to Run

```bash
pip install pandas numpy matplotlib scipy statsmodels scikit-learn
```

Place `HealthConnect_Appointment_Data.csv` in the same folder as a notebook, then run all cells top to bottom. Each notebook is self-contained and re-derives its figures directly from the raw CSV.

---

## Limitations

- The dataset is fictional and synthetic; all findings require validation against real HealthConnect operational data before any operational deployment.
- Findings are observational — they establish association, not causation.
- Risk-score thresholds (14 days, 10 km, ≥1 prior no-show) were chosen by testing a small grid of options, not formally optimised; Data Science's model is the more rigorous, data-driven alternative.
- Some patient subgroups are too small in this dataset for fully reliable segment-level conclusions.
- No live A/B test has yet been run on reminder timing or channel — this remains a recommended next step.

---

## Tools & Skills Demonstrated

**Tools:** Python, Pandas, Matplotlib, SciPy, statsmodels, scikit-learn, Jupyter Notebook, Microsoft Excel, GitHub

**Skills:** data understanding and quality assessment, data cleaning and preparation, exploratory data analysis, statistical hypothesis testing, KPI development, dashboard design, business insight generation, cross-functional collaboration, technical documentation, and stakeholder-ready presentation.

---

*Part of the AnalystLab Africa Experience Lab — HealthConnect Clinic multidisciplinary project (Project Management, Data Analytics, Data Science, ML Engineering, and Generative AI tracks).*
