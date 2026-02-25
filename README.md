# 📊 Data Analytics Portfolio

A collection of end-to-end data analytics projects spanning **SQL**, **Python**, **Power BI**, and **data storytelling**. Each project demonstrates real-world problem-solving using structured datasets and business-relevant questions.

---

## Projects Overview

### 1. E-Commerce Sales Database (SQL)
**File:** `E commerce Sales Database`

A fully structured relational database built in MySQL to simulate a small Nigerian e-commerce business.

**What it covers:**
- Database design with three normalized tables: `customers`, `products`, and `orders`
- Data insertion for 10 customers, 10 products, and 20 orders
- Business queries including:
  - All orders with customer and product details (JOINs)
  - Lagos customers who joined in 2024
  - Total revenue per product
  - Top 3 highest-spending customers
  - Products ordered more than twice (HAVING clause)
  - Customer status classification using CASE statements
  - Products never purchased and customers with no orders (LEFT JOINs)

**Tech Stack:** MySQL

---

### 2.  Nigerian House Price Analysis (Python)
**File:** `Nigeria House Prices Analysis.ipynb`

An exploratory data analysis of Nigerian real estate data to uncover pricing patterns, affordability metrics, and market segmentation.

**Key Findings:**
- **Ikoyi** is the most expensive town in Lagos, with an average property price of approximately ₦2.27 billion
- Parking spaces don't follow a linear price pattern — 8-space properties are extreme outliers (₦2.7B+)
- Property title type significantly influences median market value
- Price per bedroom is a more reliable affordability metric than average price alone

**Tech Stack:** Python (Pandas, Matplotlib/Seaborn), Jupyter Notebook

---

### 3. 📱 Customer Retention Report (Power BI)
**File:** `Customer Retention Report`

An interactive Power BI dashboard analyzing customer churn for a telecom provider across 7,043 customers.

**Key Metrics:**
| Metric | Value |
|---|---|
| Total Customers | 7,043 |
| Churned Customers | 1,869 |
| Churn Rate | 26.5% |
| Total Revenue | ₦16.06M |
| Revenue Lost to Churn | ₦4.26M |

**Key Insights:**
- Month-to-month contract holders churn at **51.4%** — the highest risk segment
- Fiber optic users are **2.89x** more likely to churn than other internet service users
- Electronic check payment method correlates with **2.65x** higher churn likelihood
- Churn is highest in the first 12 months (47.4%), dropping to just 6.6% after 60 months

**Recommendations:** Promote long-term contracts via loyalty incentives, investigate Fiber Optic service satisfaction, and improve onboarding for new customers in months 1–6.

**Tech Stack:** Power BI Desktop (DAX, Key Influencers visual, CLTV analysis)

---

### 4. 🏪 Superstore Analytics Dashboard (Power BI)
**File:** `Superstore Analytics Dashboard.pdf`

A performance dashboard for a US retail superstore tracking sales, profit, and returns across product categories and states.

**Key Metrics:**
| Metric | Current | vs. Previous Year |
|---|---|---|
| Sales | $1.17M | +40.07% |
| Profit | $136.37K | +51.35% |
| Return Rate | 11.26% | -5.77% |

**Highlights:**
- Technology (Copiers, Phones, Accessories) drives the highest profits
- Furniture (especially Tables) shows **negative profit margins**
- Return rate improved significantly year-over-year
- Sales trend shows consistent growth from 2020 to 2023

**Tech Stack:** Power BI Desktop

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| MySQL | Relational database design & querying |
| Python | Data cleaning, EDA, visualization |
| Power BI | Interactive dashboards & business reporting |
| Jupyter Notebook | Python-based data analysis |

---

## About

These projects were completed  with a focus on practical, business-driven questions and clean, interpretable outputs. Each project reflects the full analytics workflow — from raw data to actionable insight.

---

>  *Feel free to explore each project folder, and reach out with any questions or feedback!*
