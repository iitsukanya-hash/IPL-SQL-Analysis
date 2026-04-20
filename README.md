# 🏏 IPL Players SQL Analysis

A structured SQL project analyzing IPL 2025 player auction data — covering team spending, player pricing, and role-based insights using advanced SQL concepts.

---

## 📁 Project Structure

```
IPL_SQL_Analysis/
├── ipl_db_setup.sql        # Database creation + all INSERT statements
├── ipl_analysis_queries.sql # All analysis queries
└── README.md
```

---

## 📊 Dataset Overview

| Column | Description |
|---|---|
| `Player` | Player name (with country for overseas) |
| `Price_in_cr` | Auction price in crores (₹) |
| `Type` | Indian (capped/uncapped) or Overseas (capped/uncapped) |
| `Acquisition` | Retained / Auction / RTM |
| `Role` | Batter / Bowler / All-rounder / Batter-Wicketkeeper |
| `Team` | IPL franchise name |

- **Total Records:** ~200+ players across 10 IPL teams
- **Season:** IPL 2025 Mega Auction

---

## 🔍 Analysis Queries Covered

| # | Query | Concepts Used |
|---|---|---|
| 1 | Total team spending | `GROUP BY`, `SUM`, `ORDER BY` |
| 2 | Top 3 highest-paid all-rounders | `WHERE`, `ORDER BY DESC`, `LIMIT` |
| 3 | Highest-priced player per team | `CTE`, `MAX`, `JOIN` |
| 4 | Rank players by price per team (Top 2) | `ROW_NUMBER()`, `PARTITION BY`, `CTE` |
| 5 | Most & 2nd most expensive player per team | `ROW_NUMBER()`, `CASE WHEN`, Pivot logic |
| 6 | % contribution of each player's price to team total | `SUM() OVER (PARTITION BY)`, `CAST` |
| 7 | High / Medium / Low price brackets per team | `CASE WHEN`, `CTE`, `COUNT` |
| 8 | Avg price: Indian vs Overseas players | `UNION ALL`, `AVG`, `LIKE`, `GROUP BY CASE` |
| 9 | Players earning above their team's avg price | Correlated Subquery |
| 10 | Most expensive player per role | Window Function (`MAX OVER PARTITION BY`) — optimized over correlated subquery |

---

## 💡 Key SQL Concepts Demonstrated

- **CTEs** (`WITH` clause) for readable multi-step logic
- **Window Functions** — `ROW_NUMBER()`, `SUM() OVER()`, `MAX() OVER()`
- **Correlated Subqueries** and their performance tradeoffs
- **Conditional Aggregation** using `CASE WHEN` inside `MAX()`
- **UNION ALL** for combining result sets
- **Pattern matching** with `LIKE`
- **CAST** for decimal precision formatting

---

## ▶️ How to Run

```sql
-- Step 1: Create and use the database
CREATE DATABASE ipl_db;
USE ipl_db;

-- Step 2: Run ipl_db_setup.sql to create table and insert data

-- Step 3: Run ipl_analysis_queries.sql for all analysis
```

**Requirements:** MySQL 8.0+ (Window Functions support needed)

---
## 📌 Sample Insights

- 💰 **Highest paid player:** Rishabh Pant — ₹27 Cr (Lucknow Super Giants)
- 🏆 **Highest team spend:** Lucknow Super Giants
- 🌍 **Overseas avg price** vs **Indian avg price** compared via `UNION ALL`
- 📊 Majority of players fall in the **Low (<5 Cr)** price bracket

---

## 🛠 Tools Used

- **MySQL 8.0**
- **MySQL Workbench**

---

## 👩‍💻 Author

**Sukanya Saha **
PhD Scholar | Data Science Enthusiast

📧 iitsukanya@gmail.com
