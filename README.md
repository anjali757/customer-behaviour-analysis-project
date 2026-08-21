 Customer Shopping Behavior Analysis

## Project Overview
This project analyzes customer shopping behavior using transactional data from **3,900 purchases** across various product categories. The goal is to uncover insights into spending patterns, customer segments, product preferences, and subscription behavior to guide strategic business decisions.



##  Dataset Summary

| Detail | Value |
|---|---|
| Rows | 3,900 |
| Columns | 18 |
| Missing Data | 37 values in `Review Rating` column |

Key Features:
 **Customer Demographics:** Age, Gender, Location, Subscription Status
 **Purchase Details:** Item Purchased, Category, Purchase Amount, Season, Size, Color
 **Shopping Behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type



##  Tools & Tech Stack
 **Python** (pandas) — data cleaning, exploration, feature engineering
 **PostgreSQL** — structured SQL analysis of business questions
 **Power BI** — interactive dashboard for visual insights



##  Project Workflow

### 1. Exploratory Data Analysis (Python)
 **Data Loading:** Imported dataset using `pandas`
 **Initial Exploration:** Used `df.info()` and `.describe()` for structure and summary statistics
 **Missing Data Handling:** Imputed missing `Review Rating` values using the median rating per product category
 **Column Standardization:** Renamed columns for readability
 **Feature Engineering:**
  - Created `age_group` column by binning customer ages
  - Created `purchase_frequency_days` column from purchase data
- **Data Consistency Check:** Verified redundancy between `discount_applied` and `promo_code_used`; dropped `promo_code_used`
- **Database Integration:** Loaded the cleaned DataFrame into PostgreSQL for SQL analysis

### 2. Business Analysis (SQL)
Ten key business questions were answered using PostgreSQL queries:

| # | Analysis | Key Finding |
|---|---|---|
| 1 | Revenue by Gender | Male: $157,890 vs. Female: $75,191 |
| 2 | High-Spending Discount Users | 839 customers used discounts while spending above average |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78) |
| 4 | Shipping Type Comparison | Express avg. $60.48 vs. Standard avg. $58.46 |
| 5 | Subscribers vs. Non-Subscribers | Non-subscribers generate far higher total revenue ($170,436 vs. $62,645) |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), Pants (47.37%) |
| 7 | Customer Segmentation | Loyal: 3,116, Returning: 701, New: 83 |
| 8 | Top 3 Products per Category | e.g., Jewelry & Blouse lead Accessories/Clothing |
| 9 | Repeat Buyers & Subscriptions | 958 repeat buyers (>5 purchases) subscribe vs. 2,518 who don't |
| 10 | Revenue by Age Group | Young Adult ($62,143) leads, followed by Middle-aged, Adult, Senior |

### 3. Dashboard (Power BI)
An interactive **Customer Behavior Dashboard** was built featuring:
- Key metrics: Number of Customers (3.9K), Average Purchase Amount ($59.76), Average Review Rating (3.75)
- Breakdown of customers by subscription status (27% Yes / 73% No)
- Revenue and sales by category
- Revenue and sales by age group
- Filters for Subscription Status, Gender, Category, and Shipping Type



## Business Recommendations
- **Boost Subscriptions** — Promote exclusive benefits for subscribers
- **Customer Loyalty Programs** — Reward repeat buyers to move them into the "Loyal" segment
- **Review Discount Policy** — Balance sales boosts with margin control
- **Product Positioning** — Highlight top-rated and best-selling products in campaigns
- **Targeted Marketing** — Focus efforts on high-revenue age groups and express-shipping users



##  Project Structure (Suggested)

customer-shopping-behavior-analysis/
│
├── data/
        └── customer_behaviour_data.csv
├── notebooks/
         └── customer_behaviour.ipynb
├── sql/
         └── customer_analysis_filee.sql
├── dashboard/
         └── customer_behavior_dashboard.pbix
├── README.md
          └── customer_behaviour_analysis.pdf (description report)   and a presentation pdf





##  How to Reproduce
1. Clone the repository and install dependencies (`pandas`, `psycopg2` or `sqlalchemy`)
2. Run the data cleaning notebook to generate the processed dataset
3. Load the cleaned data into PostgreSQL using the provided connection script
4. Execute the SQL queries in `sql/business_queries.sql` to reproduce the analysis
5. Open the `.pbix` file in Power BI to explore the interactive dashboard


##  License
This project is intended for educational and portfolio purposes.

