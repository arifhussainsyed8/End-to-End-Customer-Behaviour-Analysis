# 🛍️ Customer Shopping Behavior Analysis

An end-to-end data analytics project exploring customer purchasing patterns, segmentation, and product preferences across 3,900 transactions — from raw data to interactive dashboard.

---

## 📌 Project Overview

This project analyzes customer shopping behavior to uncover actionable business insights. The full pipeline covers data cleaning in Python, structured querying in SQL, and visual storytelling through a Power BI dashboard and a Gamma presentation.

**Business Questions Answered:**
- Which customer segments generate the most revenue?
- How does discount usage affect spending behavior?
- What are the top-rated and best-selling products by category?
- Do subscribers spend more than non-subscribers?
- Which age groups and genders contribute the most revenue?

---

## 📂 Dataset

| Property | Details |
|---|---|
| Rows | 3,900 |
| Columns | 18 |
| Missing Data | 37 values in `review_rating` (imputed using category median) |

**Key Features:**
- **Demographics:** Age, Gender, Location, Subscription Status
- **Purchase Info:** Item, Category, Amount (USD), Season, Size, Color
- **Behavior:** Discount Applied, Previous Purchases, Purchase Frequency, Review Rating, Shipping Type

---

## 🛠️ Tools & Technologies

| Layer | Tool |
|---|---|
| Data Cleaning & EDA | Python (pandas) |
| Database | PostgreSQL |
| Dashboard | Power BI |
| Report | PDF / Word |
| Presentation | Gamma |

---

## 🔄 Project Steps

### 1. 🐍 Exploratory Data Analysis (Python)
- Loaded the dataset using `pandas`
- Explored structure with `df.info()` and `df.describe()`
- Imputed 37 missing `review_rating` values using the **median per product category**
- Renamed columns to `snake_case` for consistency
- Engineered new features:
  - `age_group` — binned customer ages into segments
  - `purchase_frequency_days` — derived from purchase frequency data
- Dropped `promo_code_used` after confirming it was redundant with `discount_applied`
- Exported the cleaned DataFrame to PostgreSQL for SQL analysis

### 2. 🗄️ SQL Analysis (PostgreSQL)
Ran 10 structured queries to answer key business questions:

| # | Query | Insight |
|---|---|---|
| 1 | Revenue by Gender | Male: $157,890 / Female: $75,191 |
| 2 | High-Spending Discount Users | 839 customers spent above average despite discounts |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82) |
| 4 | Shipping Type Comparison | Express: $60.48 avg / Standard: $58.46 avg |
| 5 | Subscribers vs. Non-Subscribers | Non-subscribers: $170,436 total revenue |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%) |
| 7 | Customer Segmentation | Loyal: 3,116 / Returning: 701 / New: 83 |
| 8 | Top 3 Products per Category | Jewelry, Blouse, Sandals, Jacket lead their categories |
| 9 | Repeat Buyers & Subscriptions | Most repeat buyers (2,518) are non-subscribers |
| 10 | Revenue by Age Group | Young Adults lead with $62,143 |

### 3. 📊 Power BI Dashboard
Built an interactive dashboard with slicers for Subscription Status, Gender, Category, and Shipping Type.

**Visuals included:**
- KPI tiles: 3.9K Customers | $59.76 Avg Purchase | 3.75 Avg Rating
- Subscription breakdown (pie chart): 27% subscribers vs. 73% non-subscribers
- Revenue and Sales by Category (bar charts)
- Revenue and Sales by Age Group (horizontal bar charts)

### 4. 📝 Report
A detailed written report summarizing methodology, findings, and business recommendations.

### 5. 🎞️ Presentation (Gamma)
A clean slide deck built in Gamma covering the project narrative, key findings, and strategic recommendations.

---

## 📈 Key Results

- **Young Adults** are the highest-revenue age group ($62,143)
- **Male customers** generate over 2× the revenue of female customers
- Only **27% of customers** are subscribed — a major growth opportunity
- Products like **Hat, Sneakers, and Coat** are heavily discount-dependent (≈50%)
- **3,116 out of 3,900** customers are classified as Loyal

---

## 💡 Business Recommendations

- **Boost Subscriptions** — Launch targeted campaigns for the 73% non-subscriber base
- **Loyalty Programs** — Reward repeat buyers to deepen the Loyal segment
- **Discount Strategy** — Review high discount-dependency products to protect margins
- **Gender Marketing** — Develop female-focused campaigns to close the revenue gap
- **Product Promotion** — Spotlight top-rated items (Gloves, Sandals, Boots) in ads
- **Shipping Upsell** — Promote Express shipping; those users spend slightly more

---

## ▶️ How to Run

### Prerequisites
```bash
pip install pandas sqlalchemy psycopg2
```

### Steps

**1. Clone the repository**
```bash
git clone https://github.com/your-username/customer-shopping-behavior.git
cd customer-shopping-behavior
```

**2. Run the Python EDA & cleaning script**
```bash
python eda_cleaning.py
```
> This loads the dataset, cleans it, engineers features, and pushes the cleaned data to your PostgreSQL database.

**3. Set up the database**

Update the connection string in `eda_cleaning.py`:
```python
engine = create_engine("postgresql://username:password@localhost:5432/shopping_db")
```

**4. Run SQL queries**

Open `queries.sql` in pgAdmin, DBeaver, or any SQL client connected to your PostgreSQL instance and execute the queries.

**5. Open the Power BI dashboard**

Open `dashboard.pbix` in Power BI Desktop and refresh the data source to point to your database.

---

## 📁 Project Structure

```
customer-shopping-behavior/
│
├── data/
│   └── shopping_behavior.csv       # Raw dataset
│
├── notebooks/
│   └── eda_cleaning.ipynb          # Python EDA & cleaning notebook
│
├── sql/
│   └── queries.sql                 # All 10 business SQL queries
│
├── dashboard/
│   └── dashboard.pbix              # Power BI dashboard file
│
├── report/
│   └── Customer_Shopping_Report.pdf
│
├── presentation/
│   └── Customer_Shopping_Gamma.pdf
│
└── README.md
```

---

## 🤝 Connect

Feel free to reach out or connect on [LinkedIn](https://linkedin.com/in/your-profile) if you have questions or feedback!
