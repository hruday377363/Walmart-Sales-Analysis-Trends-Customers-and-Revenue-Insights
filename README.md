# Walmart-Sales-Analysis-Trends-Customers-and-Revenue-Insights

### **Sales Case Study**  

#### **Objective**  
This project focuses on analyzing Walmart sales data to uncover insights about top-performing branches and products, sales trends, and customer behavior. The ultimate aim is to provide recommendations for improving and optimizing sales strategies. The dataset was sourced from the **Kaggle Walmart Sales Forecasting Competition**.  

#### **Project Context**  
The Kaggle competition provided historical sales data for 45 Walmart stores across different regions. Each store includes multiple departments, and participants were tasked with predicting department-wise sales. Adding complexity, the dataset incorporates holiday markdown events that influence sales unpredictably, both in terms of affected departments and the extent of the impact.  

#### **Purpose**  
The primary goal is to understand factors influencing sales across different Walmart branches and identify actionable insights for boosting sales and profitability.  

---

#### **Dataset Overview**  
The dataset, derived from Kaggle, contains 17 columns and 1000 rows, covering sales transactions from three Walmart branches in **Mandalay**, **Yangon**, and **Naypyitaw**.  

**Columns Description:**  
| Column Name            | Description                                      | Data Type         |  
|-------------------------|--------------------------------------------------|-------------------|  
| `invoice_id`           | Invoice ID for sales transactions                | VARCHAR(30)       |  
| `branch`               | Branch where the sale occurred                   | VARCHAR(5)        |  
| `city`                 | Location of the branch                           | VARCHAR(30)       |  
| `customer_type`        | Type of customer                                 | VARCHAR(30)       |  
| `gender`               | Gender of the purchasing customer                | VARCHAR(10)       |  
| `product_line`         | Category of the product                          | VARCHAR(100)      |  
| `unit_price`           | Price per unit                                   | DECIMAL(10, 2)    |  
| `quantity`             | Quantity sold                                    | INT               |  
| `VAT`                  | Tax amount on the purchase                       | FLOAT(6, 4)       |  
| `total`                | Total cost (price + VAT)                         | DECIMAL(10, 2)    |  
| `date`                 | Date of purchase                                 | DATE              |  
| `time`                 | Time of purchase                                 | TIMESTAMP         |  
| `payment_method`       | Payment method used                              | VARCHAR(30)       |  
| `cogs`                 | Cost of goods sold                               | DECIMAL(10, 2)    |  
| `gross_margin_percentage` | Gross margin percentage                        | FLOAT(11, 9)      |  
| `gross_income`         | Gross profit from the sale                       | DECIMAL(10, 2)    |  
| `rating`               | Customer rating for the transaction              | FLOAT(2, 1)       |  

---

#### **Analysis Objectives**  
1. **Product Analysis:**  
   - Identify the performance of product lines.  
   - Pinpoint best- and worst-performing categories.  

2. **Sales Analysis:**  
   - Analyze sales trends across branches, product lines, and time periods.  
   - Assess the effectiveness of current sales strategies.  

3. **Customer Analysis:**  
   - Explore customer demographics and behaviors.  
   - Evaluate customer segment profitability.  

---

#### **Approach**  
1. **Data Wrangling:**  
   - Inspected the dataset for NULL values.  
   - Ensured missing data was managed through proper replacement methods.  
   - Null values were avoided by using the `NOT NULL` constraint during database table creation.  

2. **Feature Engineering:**  
   - Added a `time_of_day` column to classify sales into Morning, Afternoon, or Evening.  
   - Extracted the day and month from the `date` column to create `day_name` and `month_name` columns.  

3. **Exploratory Data Analysis (EDA):**  
   - Analyzed sales trends, customer behaviors, and product performance using the modified dataset.  

---

#### **Business Questions Addressed**  

**Generic Questions:**  
- How many unique cities are included?  
- Which branch is located in which city?  

**Product Analysis:**  
- How many unique product lines exist?  
- What is the most common payment method?  
- Which product line generates the highest revenue?  
- Which city contributes the most revenue?  
- What product line generates the most VAT?  

**Sales Analysis:**  
- When during the day are the most sales made?  
- Which customer type generates the most revenue?  
- Which city pays the highest VAT?  

**Customer Analysis:**  
- What is the gender distribution of customers across branches?  
- What time of day receives the best customer ratings?  
- Which day of the week records the highest average ratings?  

---

#### **Revenue and Profit Calculations**  
1. **Cost of Goods Sold (COGS):**  
   \[ \text{COGS} = \text{unit\_price} \times \text{quantity} \]  

2. **Value-Added Tax (VAT):**  
   \[ \text{VAT} = 0.05 \times \text{COGS} \]  

3. **Total Revenue (Gross Sales):**  
   \[ \text{Total} = \text{COGS} + \text{VAT} \]  

4. **Gross Profit:**  
   \[ \text{Gross Profit} = \text{Total} - \text{COGS} \]  

5. **Gross Margin Percentage:**  
   \[ \text{Gross Margin \%} = \left( \frac{\text{Gross Profit}}{\text{Total Revenue}} \right) \times 100 \]  

**Example Calculation (First Row):**  
- **Unit Price:** $45.79  
- **Quantity:** 7  
- **COGS:** $45.79 × 7 = $320.53  
- **VAT:** $0.05 × $320.53 = $16.03  
- **Total Revenue:** $320.53 + $16.03 = $336.56  
- **Gross Margin Percentage:** $(16.03 / 336.56) × 100 ≈ 4.76\%$  
