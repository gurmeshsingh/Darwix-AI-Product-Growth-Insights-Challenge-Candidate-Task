# Darwix-AI-Product-Growth-Insights-Challenge-Candidate-Task


# Darwix AI – Product Growth & Insights (Part 1)

> **Scope (Part 1):** Core engagement metrics, feature adoption, retention, repeat-session correlations, and behavioral hypotheses + validation plans.

---

## 📌 TL;DR Results (from my run)

- **Avg DAU:** `533.34`
- **Avg WAU:** `1,749`
- **DAU/WAU ratio:** `0.305` (healthy daily consistency)

### Feature Adoption (unique users who tried the feature at least once / total users)

| Feature              | Users Used Feature | Adoption % |
|---|---:|---:|
| api_integration      | 6,035 | 60.35 |
| dashboard_view       | 6,004 | 60.04 |
| document_analysis    | 5,994 | 59.94 |
| ai_assistant         | 5,989 | 59.89 |
| lead_scoring         | 5,964 | 59.64 |
| report_generation    | 5,963 | 59.63 |
| data_export          | 5,951 | 59.51 |
| analytics_deep_dive  | 5,934 | 59.34 |
| team_collaboration   | 5,921 | 59.21 |
| sales_insights       | 5,884 | 58.84 |
| custom_workflows     | 5,867 | 58.67 |
| email_automation     | 5,866 | 58.66 |

### Retention (share of new users who returned on Day N)

| Day 1 | Day 2 | Day 3 |
|---:|---:|---:|
| 36.82% | 26.06% | 2.45% |

> *Note:* D7 / D30 retention were computed in SQL (methods below) and can be added alongside when needed.

### Features most associated with **repeat sessions** (share of feature users who are repeat users)

| Feature              | Repeat-User Share % |
|---|---:|
| custom_workflows     | **97.06** |
| document_analysis    | 97.01 |
| team_collaboration   | 96.89 |
| email_automation     | 96.81 |
| analytics_deep_dive  | 96.77 |
| dashboard_view       | 96.74 |
| sales_insights       | 96.72 |
| api_integration      | 96.72 |
| ai_assistant         | 96.72 |
| data_export          | 96.69 |
| report_generation    | 96.68 |
| lead_scoring         | 96.62 |

---

## 🧮 Metric Definitions

- **DAU (Daily Active Users):** count of unique users with ≥1 session on a calendar day.
- **WAU (Weekly Active Users):** unique users with ≥1 session in a calendar week.
- **Feature Adoption:** % of all users who used a given feature at least once.
- **Retention (D1/D7/D30):** % of a signup cohort that returns exactly on day 1/7/30 after signup.
- **Repeat User:** user with more than one session overall (or on >1 distinct day).

---

## 🔧 Reproducible SQL (DuckDB/Postgres-style)

> Tables used:
> - `user_data(user_id, signup_date, channel, region)`
> - `sessions_data(session_id, user_id, start_time, end_time, device_type)`
> - `feature_usage_data(session_id, feature_name, usage_timestamp)`

## 🧠 Behavioral Hypotheses (with Validation Plans)

### 1) Early Workflow Creation → Higher Retention
**Hypothesis:** Users who build a **custom workflow** in their first session have higher **D7 retention**.  
**Validate:** Split new users into two cohorts based on Day 0–1 behavior and compare outcomes.

- **Cohorts**
  - Cohort A: Used `custom_workflows` on Day 0–1
  - Cohort B: Did **not** use `custom_workflows` on Day 0–1
- **Primary Metric:** D7 Retention (% users active exactly 7 days after signup)
- **Secondary Metrics:** Repeat-user rate (>1 session in Week 1), Sessions/user (Week 1), Time-to-first-transaction (if applicable)
- **Success Criteria:** Cohort A shows statistically significant ↑ in D7 retention vs Cohort B (e.g., +20% relative lift)

---

### 2) Collaboration → More Repeat Sessions
**Hypothesis:** Users who engage with **team_collaboration** (share, comment, invite) are more likely to return multiple times within a week.  
**Validate:** Compare repeat behavior between collaboration users and non-collab users.

- **Segments**
  - Segment C: Used `team_collaboration` in Week 1
  - Segment D: Did **not** use `team_collaboration` in Week 1
- **Primary Metric:** Repeat-session rate (≥2 sessions in Week 1)
- **Secondary Metrics:** WAU inclusion (active ≥1 time that ISO week), Session frequency (Week 1), Day-7 retention
- **Success Criteria:** Segment C has higher repeat-session rate and WAU inclusion vs Segment D (statistically significant)

---

### 3) Analytics/Dashboard → Long-term Stickiness
**Hypothesis:** Users who access **analytics_deep_dive** or **dashboard_view** in Week 1 have higher **D30 retention**.  
**Validate:** Compare long-term retention and engagement depth between analytics users and non-users.

- **Segments**
  - Segment E: Used `analytics_deep_dive` OR `dashboard_view` in Week 1
  - Segment F: Did **not** use these features in Week 1
- **Primary Metric:** D30 Retention (% active exactly 30 days after signup)
- **Secondary Metrics:** Sessions/user (Days 8–30), Return days (count of distinct active days in Days 8–30)
- **Success Criteria:** Segment E shows statistically significant ↑ in D30 retention vs Segment F

---
