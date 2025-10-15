# 📊 Darwix AI – Product Growth & Insights Challenge

**Candidate Task**: Step into the role of a Product Manager and transform data into actionable growth strategies.

---
**Part 1** : Product Metrics & Behavioral Analysis

## 🧩 Overview

**Objective:**  
Understand user behavior and engagement patterns through key product metrics.

**Datasets used:**
- `user_data (user_id, signup_date, channel, region)`
- `sessions_data (session_id, user_id, start_time, end_time, device_type)`
- `feature_usage_data (session_id, feature_name, usage_timestamp)`
- `feedback_data (feedback_id, user_id, rating, feature_name, comments, session_id)`

---

## 📈 Metrics & Results


### 🟢 **Daily Active Users (DAU)**
**Definition:**  
The number of unique users who have at least one active session on a given calendar day.

**Purpose:**  
DAU measures daily engagement — how many users actively use the product each day.  
It’s a core indicator of short-term user activity and overall product “habit strength.”

### 🔵 **Weekly Active Users (WAU)**

**Definition:**
The number of unique users who have at least one active session during a 7-day period (calendar week).

**Purpose:**
WAU measures weekly engagement and helps identify medium-term user stickiness.

### 🔹 Engagement Metrics

| Metric | Result |
|--------|--------:|
| **Average DAU** | 533.34 |
| **Average WAU** | 1,749 |

---
## 🚀 Feature Adoption Rate

### 🧩 Definition
**Feature Adoption Rate** measures what percentage of all users have used a particular feature at least once.  
It helps identify which product functionalities are being discovered and actually used by your user base.

\[
Feature\ Adoption\ Rate = 
\frac{\text{Unique Users Who Used a Feature}}{\text{Total Registered Users}} \times 100
\]

---

### 🎯 Purpose
Feature adoption tells you **which features drive engagement and which ones need visibility or improvement**.

- High adoption → Feature is intuitive, valuable, and well-integrated into user flow.  
- Low adoption → Users may not know about it, or it may lack immediate value.

It’s one of the clearest signals of **product-market fit at the feature level**.

---

### 🧮 Example Results (from analysis)

| Feature | Users Used Feature | Adoption % |
|----------|-------------------:|------------:|
| api_integration | 6,035 | 60.35 |
| dashboard_view | 6,004 | 60.04 |
| document_analysis | 5,994 | 59.94 |
| ai_assistant | 5,989 | 59.89 |
| lead_scoring | 5,964 | 59.64 |
| report_generation | 5,963 | 59.63 |
| data_export | 5,951 | 59.51 |
| analytics_deep_dive | 5,934 | 59.34 |
| team_collaboration | 5,921 | 59.21 |
| sales_insights | 5,884 | 58.84 |
| custom_workflows | 5,867 | 58.67 |
| email_automation | 5,866 | 58.66 |

💡 *Insight:*  
Most features show **~59–60% adoption**, indicating strong baseline engagement, but **custom_workflows** has slightly lower adoption despite having the **highest repeat-u_**

### 🔹 Feature Adoption Rate

Percentage of total users who have used each feature at least once.

| Feature | Users Used Feature | Adoption % |
|----------|-------------------:|------------:|
| api_integration | 6,035 | 60.35 |
| dashboard_view | 6,004 | 60.04 |
| document_analysis | 5,994 | 59.94 |
| ai_assistant | 5,989 | 59.89 |
| lead_scoring | 5,964 | 59.64 |
| report_generation | 5,963 | 59.63 |
| data_export | 5,951 | 59.51 |
| analytics_deep_dive | 5,934 | 59.34 |
| team_collaboration | 5,921 | 59.21 |
| sales_insights | 5,884 | 58.84 |
| custom_workflows | 5,867 | 58.67 |
| email_automation | 5,866 | 58.66 |

---

### 🔹 Retention Rate

| Day | Retention % |
|-----|-------------:|
| Day 1 | 36.82% |
| Day 7 | 26.06% |
| Day 30 | 2.45% |

---

### 🔹 Features Most Correlated With Repeat Sessions

| Feature | Repeat-User Share % |
|----------|-------------------:|
| custom_workflows | **97.06** |
| document_analysis | 97.01 |
| team_collaboration | 96.89 |
| email_automation | 96.81 |
| analytics_deep_dive | 96.77 |
| dashboard_view | 96.74 |
| sales_insights | 96.72 |
| api_integration | 96.72 |
| ai_assistant | 96.72 |
| data_export | 96.69 |
| report_generation | 96.68 |
| lead_scoring | 96.62 |

---

## 🧠 Behavioral Hypotheses (With Validation Plans)

### 1️⃣ Early Workflow Creation → Higher Retention

**Observation:**  
- `custom_workflows` has the highest repeat-user share (97.06%) but only ~59% adoption.  
- Indicates early workflow creation may lead to habit formation.

**Hypothesis:**  
Users who create a **custom workflow** in their first session have higher D7 retention.

**Validation Plan:**  
- Split users into two cohorts:  
  - **A:** Used `custom_workflows` in Day 0–1  
  - **B:** Did not use it  
- Compare **D7 retention** and **repeat-session rate** between both groups.

**Expected Outcome:**  
Cohort A shows higher D7 retention and repeat engagement.

---

### 2️⃣ Collaboration Features → More Repeat Sessions

**Observation:**  
- `team_collaboration` shows a 96.9% repeat-user share.  
- Suggests social or shared actions drive repeat visits.

**Hypothesis:**  
Users who use **team_collaboration** features are more likely to return multiple times in a week.

**Validation Plan:**  
- Compare users who used `team_collaboration` in Week 1 vs. those who didn’t.  
- Measure **repeat-session rate (≥2 sessions/week)** and **WAU participation**.

**Expected Outcome:**  
Collaboration users have a higher repeat-session rate and weekly engagement.

---

### 3️⃣ Analytics/Dashboard Features → Long-Term Retention

**Observation:**  
- `analytics_deep_dive` and `dashboard_view` have ~60% adoption and 96.7% repeat-user share.  
- Indicates users who monitor outcomes are more likely to stick around.

**Hypothesis:**  
Users who access **analytics or dashboard features** in their first week are more likely to remain active at Day 30.

**Validation Plan:**  
- Segment users based on use of `analytics_deep_dive` or `dashboard_view` during Week 1.  
- Compare **D30 retention** between both groups.

**Expected Outcome:**  
Analytics users show higher D30 retention and more sessions beyond the first week.

---

## 🔍 Key Insights

- **Personalization (custom workflows)** drives short-term engagement.  
- **Collaboration** creates network loops that boost weekly activity.  
- **Analytics & dashboards** build long-term product stickiness.  

Improving discovery of these features during early onboarding could significantly improve retention across all user segments.

---

## 🧩 Next Steps (Part 2)

- Funnel Visualization & Drop-off Analysis  
- A/B Test Plan for Activation Improvement  
- Product Change Proposal for Better Conversion  

