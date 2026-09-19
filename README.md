# Weekend vs Weekday Sales in Q4 2022

## 📊 Project Objective
The Campaign Team wants to analyze whether weekend promotions were effective during the last quarter of 2022. This project calculates the average daily sales using `before_discount` for weekends (Saturday and Sunday) and weekdays (Monday to Friday) between October and December 2022, using `order_date` to extract day and month information. The average sales for weekends and weekdays are compared both **monthly** and **overall** to determine if sales were higher during weekends.

## 🧮 Calculated Fields
```
Day_Type = CASE WHEN WEEKDAY(order_date) IN (5,6) THEN "Weekend" ELSE "Weekday" END

Is_Q4_2022 = CASE WHEN YEAR(order_date) = 2022 AND MONTH(order_date) IN (10,11,12) THEN "Yes" ELSE "No" END
```

## 🗂️ Dataset
**File:** `Sale_data_2022_Payment_Method`

**Columns used:**
| Column | Description |
|---|---|
| `order_date` | Date of the order (used to extract day type and month) |
| `before_discount` | Order value before discount (used as the sales metric) |

## 📈 Visualizations
1. **Table:** Monthly average sales — `Day_Type` x `order_date (Year Month)` x `AVG(before_discount)`
2. **Bar Chart:** Grouped bar chart — Dimension: `order_date (Year Month)`, Breakdown: `Day_Type`, Metric: `AVG(before_discount)`
- **Filter applied:** `Is_Q4_2022 = Yes` (Oct, Nov, Dec 2022 only)

## 📷 Screenshot
Weekend vs Weekday Sales Analysis - Q4 2022(img width="2500" height="1876" alt="Weekend_vs_Weekday_Sales_Analysis_-_Q4_2022-1" src="https://github.com/user-attachments/assets/5423505a-8d3a-4c76-8416-1aba01ddaead")

## 🔍 Key Insight

**Overall Q4 2022 comparison:**
| Day Type | Average Sales (before_discount) |
|---|---|
| Weekday | 3,953.20 |
| Weekend | 3,819.79 |

**Monthly breakdown:**
| Month | Weekday Avg | Weekend Avg | Higher |
|---|---|---|---|
| October 2022 | 3,004.90 | 3,320.51 | Weekend |
| November 2022 | 3,952.57 | 3,641.16 | Weekday |
| December 2022 | 4,747.82 | 4,282.89 | Weekday |

**Conclusion:** Overall, weekday sales were slightly higher than weekend sales in Q4 2022. Weekend promotions appeared effective only in **October**, while **November and December** saw stronger weekday performance. This suggests weekend promotions did not consistently drive higher sales throughout the quarter.

## 🔗 Live Report
**Looker Studio Report:** [Weekend vs Weekday Sales Analysis - Q4 2022](https://datastudio.google.com/reporting/65be948d-094f-435e-bb7c-ee8ef6118eb5)

## 🛠️ Tools Used
- Google Sheets (data source)
- Looker Studio (visualization)


## 👤 Author
**Sahil Kumar**
