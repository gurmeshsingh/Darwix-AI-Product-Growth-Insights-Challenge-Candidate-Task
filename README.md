# Darwix AI – Product Growth & Insights Challenge (SQL + Product Metrics)

This project simulates a Product Manager / Product Analyst workflow: turning product usage data into actionable insights to improve **retention**, **feature adoption**, and reduce **onboarding drop-offs**.

Everything here is designed to be **simple, interview-explainable**, and directly runnable in **MySQL**.

---

##  Dataset Overview

We are provided with 4 CSV tables:

### 1. `users`
**Columns:** `user_id, signup_date, channel, region`  
**Purpose:** User acquisition + segmentation (cohorts, channels, regions).

### 2. `sessions`
**Columns:** `session_id, user_id, start_time, end_time, device_type`  
**Purpose:** Core activity table. A user is considered **active** if they have a session.

### 3. `feature_usage`
**Columns:** `session_id, feature_name, usage_timestamp`  
**Purpose:** Feature adoption and engagement tracking within sessions.

### 4. `feedback`
**Columns:** `feedback_id, user_id, rating, feature_name, comments, session_id`  
**Purpose:** User sentiment on features and experience, tied to sessions.

---
## PART 1 : Product Metrices and Behavioral Analysis


###  Key Definitions Used

- **Active user:** A user with at least one session (`sessions` table).
- **DAU:** Unique active users per day.
- **WAU:** Unique active users per week.
- **Feature Adoption Rate:** % of active users who used a feature at least once.
- **Retention (D1/D7/D30):** % of users who return **exactly** N days after signup.
- **Repeat user:** A user with more than 1 session.

---

## 1.1 Calculating Metrices using SQL Queries (MySQL)

#### A) Daily Active Users (DAU)

<img width="600" height="500" alt="Screenshot 2025-12-21 004313" src="https://github.com/user-attachments/assets/7406d40f-5fce-41e4-bbe9-d6380138dd37" />

#### B) Weekly Active Users (WAU)

<img width="550" height="500" alt="Screenshot 2025-12-21 004725" src="https://github.com/user-attachments/assets/6f9a9cc9-854b-4069-a2ab-2db1e185b09b" />

#### C) Feature Adoption Rate

<img width="500" height="600" alt="Screenshot 2025-12-21 004945" src="https://github.com/user-attachments/assets/e03296d2-3f04-4cfd-a2dd-8bd6ede8bc61" />

#### D) Retention Rate Day 1, 7, 30

<img width="700" height="500" alt="Screenshot 2025-12-21 173007" src="https://github.com/user-attachments/assets/7f48d3b0-dc51-417a-bbcf-8e1cf491485b" />




## 1.2 Features most strongly correlated with repeat sessions

Repeat sessions are most strongly associated with dashboard_view, which is used by the highest number of returning users, making it the primary engagement surface. Document_analysis and ai_assistant also show strong correlation with repeat usage, indicating sustained value once users adopt them. Other features are used by fewer repeat users, suggesting they support niche or advanced use cases rather than driving core repeat behavior.


<img width="600" height="700" alt="image" src="https://github.com/user-attachments/assets/5ebcd795-89b5-4c4b-a501-132a0630ef9b" />



## 1.3 Behvioral Hypotheses and their Validations 

### **Hypothesis 1:**
### Users who do not experience core product value early are unlikely to activate

**What I believe:**
Most users drop off because they fail to engage with the product’s core features (dashboard view, document analysis, AI assistant) before completing their first transaction.

**Why I believe this:**
Core features are heavily used by repeat users, yet overall activation is low (only 28%). This suggests many users leave before reaching the point where value becomes clear.

**How I would validate:**
Compare activation and Day-1 retention between users who interacted with at least one core feature in their first session and those who did not. If users who touched a core feature activate and retain at a meaningfully higher rate, the hypothesis holds.

## **Hypothesis 2:** 
### The product lacks a clear “push” from account creation to first transaction

**What I believe:**
After account creation, users are unsure what to do next, leading to a 72% drop-off before the first transaction.

**Why I believe this:**
The sharp funnel drop happens immediately after signup, not later in the journey. This points to friction, confusion, or lack of guidance rather than dissatisfaction with advanced functionality.

**How I would validate:**
Track time-to-first-transaction and first-session behavior. If most users drop without performing any meaningful action (feature usage, setup, transaction attempt), it confirms that onboarding is not effectively guiding users forward.

## **Hypothesis 3:**
### Advanced features support engagement only after users are already retained

**What I believe:**
Advanced features (custom workflows, analytics deep dive, API integration) do not drive early activation and are mainly used by already-engaged users.

**Why I believe this:**
These features have low overall adoption but appear among repeat users, suggesting they add depth rather than initial value.

**How I would validate:**
Compare early retention of users who interacted with advanced features in their first session versus those who did not. If early retention does not improve, it confirms these features should be introduced later in the user journey.
