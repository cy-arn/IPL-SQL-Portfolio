#  IPL 2025 & 2026 — SQL Analytics Portfolio

> **A data analytics project exploring batting and bowling performances across two IPL seasons using structured SQL queries on real match statistics.**

---

##  Project Overview

This project performs **SQL-driven analysis** on IPL player statistics for the **2025 and 2026 seasons**. It answers 10 targeted analytical questions spanning batting performance, bowling efficiency, cross-season comparisons, and milestone tracking — all using a single SQL dialect against a structured relational schema (`ipl_stats`).

The project is designed as a **portfolio piece** to demonstrate applied SQL skills including filtering, aggregation, joins, and performance ranking — visualized through a companion dashboard.

---

##  Repository Structure

```
ipl-sql-analytics/
│
├── SQL_basic_queries.txt     # All 10 SQL queries with comments
│
├──  results/                  # Query output CSVs
│   ├── Q2.csv                   # Top SR ≥ 140 batsman — 2025
│   ├── Q3.csv                   # Top SR ≥ 140 batsman — 2026
│   ├── Q4.csv                   # Best bowler (Econ ≤ 8) — 2025
│   ├── Q7.csv                   # 4-wicket hauls — 2026
│   ├── Q8.csv                   # Bowlers with least overs — 2025
│   ├── Q9.csv                   # Top team by runs — 2026
│   └── Q10.csv                  # Half-century leaders (combined)
│
└── README.md
```

---

## Database Schema

The dataset is hosted under the `ipl_stats` schema and contains four tables:

| Table | Description |
|---|---|
| `ipl_stats.2025_batsmen` | Batting stats for IPL 2025 — Runs, SR, 4s, 6s, 50s |
| `ipl_stats.2025_bowlers` | Bowling stats for IPL 2025 — Wkts, Overs, Econ, 4w |
| `ipl_stats.2026_batsmen` | Batting stats for IPL 2026 — Runs, SR, 4s, 6s, 50s |
| `ipl_stats.2026_bowlers` | Bowling stats for IPL 2026 — Wkts, Overs, Econ, 4w |

---

## Questions & Key Findings

### Batting Analysis

| # | Question | Answer |
|---|---|---|
| Q1 | Most wickets — IPL 2025? | **M Prasidh Krishna** (GT) — 25 Wkts |
| Q2 | Highest runs with SR ≥ 140 — 2025? | **B Sai Sudharsan** (GT) — 759 Runs @ SR 156.17 |
| Q3 | Highest runs with SR ≥ 140 — 2026? | **H Klaasen** (SRH) — 508 Runs @ SR 153.93 |
| Q5 | Most runs across both seasons combined? | **B Sai Sudharsan** — highest combined total |
| Q6 | Maximum boundaries (4s + 6s) — 2025? | **B Sai Sudharsan** — 109 total boundaries |

### Bowling Analysis

| # | Question | Answer |
|---|---|---|
| Q4 | Most wickets with Economy ≤ 8 — 2025? | **JJ Bumrah** (MI) — 18 Wkts @ Econ 6.67 |
| Q7 | Bowlers with 4-wicket hauls — 2026? | **5 bowlers**: B Kumar, Rashid Khan, E Malinga, J Overton, M Prasidh Krishna |
| Q8 | Bowlers with least overs bowled — 2025? | A Badoni (1.4 ov), P Dubey (2 ov), K Khejroliya (3 ov), RJ Gleeson (3.3 ov), AS Roy (4 ov) |

### Cross-Season Analysis

| # | Question | Answer |
|---|---|---|
| Q9 | Team with maximum runs — 2026? | **SRH** — 508 Runs |
| Q10 | Most half-centuries across both seasons? | **3-way tie** — B Sai Sudharsan, V Kohli, SS Iyer (11 each) |

---

## SQL Concepts Demonstrated

| Concept | Used In |
|---|---|
| `WHERE` filtering | Q2, Q3, Q4, Q7 |
| `ORDER BY` + `LIMIT` | Q1, Q2, Q3, Q4, Q6, Q8, Q9 |
| `MAX()` aggregate | Q1, Q9 |
| `MIN()` aggregate | Q8 |
| `SUM()` aggregate | Q10 |
| `GROUP BY` | Q1, Q8, Q9, Q10 |
| `INNER JOIN` across seasons | Q5, Q10 |
| Column aliasing | All queries |
| Computed columns (`_4s + _6s`, `bt25.Runs + bt26.Runs`) | Q5, Q6, Q10 |

---

## Dashboard Preview

The SQL results were visualized as an interactive dashboard with IPL-themed styling.

**Slide 1 — IPL 2025 Season Analysis**

![IPL 2025 Dashboard](dashboard_2025.png)

**Slide 2 — IPL 2026 Season & Cross-Season Analysis**

![IPL 2026 Dashboard](dashboard_2026.png)

> Dashboards include KPI cards, horizontal bar charts, bowling performance tables, and cross-season comparison charts.

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **SQL** | Core analysis — all 10 queries |
| **MySQL / BigQuery** | Query execution environment |
| **CSV** | Exported query results |
| **Data Visualization** | Dashboard built from query outputs |

---

##  Key Insights

- **B Sai Sudharsan** was the standout performer of IPL 2025 — leading in runs (759), strike rate (156.17), and boundaries (109), cementing him as the Orange Cap holder.
- **JJ Bumrah** proved that economy and wickets aren't mutually exclusive — 18 wickets at just 6.67 RPO made him the most efficient bowler among all Econ ≤ 8 performers.
- **SRH** dominated the 2026 batting charts with H Klaasen anchoring the team to the highest individual run tally (508 runs at SR 153.93).
-  IPL 2026 saw **5 different bowlers** take 4-wicket hauls — a sign of well-distributed bowling strength across franchises.
- The **half-century race** ended in a remarkable 3-way tie between B Sai Sudharsan, V Kohli, and SS Iyer — all finishing with 11 fifties across both seasons.

---

## How to Run

1. Set up a database with the `ipl_stats` schema and import the 4 season tables.
2. Open `SQL_basic_queries.txt` and run queries Q1–Q10 in order.
3. Export each result as a `.csv` to reproduce the output files in `/results`.

```sql
-- Example: Run Q2 to find the top SR ≥ 140 batsman of 2025
SELECT Player, Team, Season, SR AS Strike_Rate, Runs
FROM ipl_stats.2025_batsmen
WHERE SR >= 140
ORDER BY Runs DESC
LIMIT 1;
```

---

## Author

**Arnab Chakraborty**

[![LinkedIn](https://www.linkedin.com/in/arnabchakraborty99/)
[![GitHub](https://github.com/cy-arn)

---

> *Built with SQL. Driven by cricket.* 

