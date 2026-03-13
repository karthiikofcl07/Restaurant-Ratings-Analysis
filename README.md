<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f0c29,50:302b63,100:24243e&height=200&section=header&text=Restaurant%20Ratings%20Analysis&fontSize=42&fontColor=ffffff&fontAlignY=38&desc=Cognifyz%20Technologies%20·%20Data%20Analytics%20Internship&descAlignY=58&descSize=16&descColor=a78bfa&animation=fadeIn" />

</div>

<div align="center">

<a href="https://python.org"><img src="https://img.shields.io/badge/Python_3.10+-3776AB?style=for-the-badge&logo=python&logoColor=FFD43B" /></a>
<a href="https://jupyter.org"><img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" /></a>
<a href="https://pandas.pydata.org"><img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" /></a>
<a href="https://seaborn.pydata.org"><img src="https://img.shields.io/badge/Seaborn-4EACD8?style=for-the-badge&logo=python&logoColor=white" /></a>
<a href="https://matplotlib.org"><img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white" /></a>
<img src="https://img.shields.io/badge/Status-Completed-22c55e?style=for-the-badge&logo=checkmarx&logoColor=white" />

<br/><br/>

<img src="https://img.shields.io/badge/Records-9%2C551_Restaurants-6366f1?style=flat-square&logo=databricks&logoColor=white" />
<img src="https://img.shields.io/badge/Features-21_Columns-8b5cf6?style=flat-square&logo=tableau&logoColor=white" />
<img src="https://img.shields.io/badge/Countries-15_Nations-a78bfa?style=flat-square&logo=googlemaps&logoColor=white" />
<img src="https://img.shields.io/badge/Task-Level_1_·_Task_3-c4b5fd?style=flat-square" />

</div>

<br/>

<div align="center">

```

```

</div>

---

## 📋 Table of Contents

<div align="center">

| Section | Description |
|:-------:|:------------|
| [🎯 Overview](#-task-overview) | Objectives, scope & business context |
| [📐 Architecture](#-project-architecture) | Folder structure & file map |
| [📦 Dataset](#-dataset-schema) | Schema, fields & quick stats |
| [🔬 Methodology](#-analytical-methodology) | 8-step analysis pipeline |
| [📊 Analysis](#-analysis-breakdown) | Step-by-step walkthrough |
| [📈 Results](#-key-results--findings) | All numbers, tables, distributions |
| [🧠 Insights](#-insights--interpretation) | 5 deep-dive interpretations |
| [🖼️ Visualizations](#️-visualizations) | Chart previews & descriptions |
| [⚙️ Setup](#️-setup--installation) | Installation & launch guide |
| [🛠️ Tech Stack](#️-tech-stack) | Libraries, versions, roles |
| [👤 Author](#-author) | Contact & socials |

</div>

---

## 🎯 Task Overview

<table>
<tr>
<td width="50%" valign="top">

### 🔎 Problem Statement

This project conducts a rigorous **statistical analysis of restaurant rating data** from Cognifyz Technologies' global restaurant intelligence dataset — spanning **9,551 restaurants across 15 countries**.

The analysis is structured around **3 precise objectives**:

1. 📊 **Distribution Analysis** — Understand how aggregate ratings are distributed across all restaurants using histogram + KDE visualizations
2. 🏆 **Modal Range Detection** — Identify which 1-point rating band (0–1, 1–2, 2–3, 3–4, 4–5) contains the highest concentration of restaurants
3. 🗳️ **Engagement Profiling** — Compute average votes per restaurant and reveal how user engagement scales with rating quality

</td>
<td width="50%" valign="top">

### 💼 Business Value

This analysis surfaces intelligence for multiple stakeholders:

| Stakeholder | Value Delivered |
|-------------|----------------|
| 📊 **Platform Analysts** | Detect rating skew and data quality issues |
| 🏢 **Business Owners** | Benchmark against industry rating norms |
| 🎨 **UX Designers** | Understand what drives engagement and reviews |
| 📣 **Marketing Teams** | Identify engagement patterns by quality tier |
| 🔬 **Data Scientists** | Baseline for predictive rating models |

> 💬 *"22.5% of restaurants are unrated — an invisible segment invisible to standard quality filters."*

</td>
</tr>
</table>

---

## 📐 Project Architecture

```
📦 restaurant-ratings-analysis/
│
├── 📓 Restaurant_Ratings_Analysis.ipynb     ← Main analysis notebook (10 cells)
├── 📊 cognifyz_Dataset_.csv                 ← Source dataset · 9,551 rows × 21 cols
├── 📄 README.md                             ← This document
│
└── 📁 outputs/                              ← Auto-generated chart exports
    ├── 🖼️  rating_distribution.png          ← Histogram + KDE density plot
    ├── 🖼️  rating_categories.png            ← Bar chart + Donut (by label)
    ├── 🖼️  rating_range.png                 ← Modal range highlight chart
    └── 🖼️  votes_analysis.png               ← Votes histogram + tier engagement
```

> 📌 All output images are **auto-saved** at 200 DPI when the notebook is run end-to-end.

---

## 📦 Dataset Schema

> **Source:** Cognifyz Technologies · Restaurant Intelligence Dataset  
> **Scope:** Global · 15 countries · 9,551 records · 21 features · Zero missing values

<details open>
<summary><b>🗂️ Full Column Reference</b></summary>

<br/>

| # | Column | Type | Description |
|---|--------|------|-------------|
| 1 | `Restaurant ID` | `int` | Unique identifier per restaurant |
| 2 | `Restaurant Name` | `str` | Restaurant display name |
| 3 | `Country Code` | `int` | Numeric country identifier (mapped to 15 nations) |
| 4 | `City` | `str` | City of operation |
| 5 | `Address` | `str` | Full street address |
| 6 | `Locality` | `str` | Neighbourhood / area |
| 7 | `Locality Verbose` | `str` | Locality + city composite label |
| 8 | `Longitude` | `float` | Geo-coordinate (longitude) |
| 9 | `Latitude` | `float` | Geo-coordinate (latitude) |
| 10 | `Cuisines` | `str` | Comma-separated cuisine types |
| 11 | `Average Cost for two` | `int` | Estimated local currency cost for 2 |
| 12 | `Currency` | `str` | Local currency name |
| 13 | `Has Table booking` | `bool` | Accepts reservations (Yes/No) |
| 14 | `Has Online delivery` | `bool` | Delivery available (Yes/No) |
| 15 | `Is delivering now` | `bool` | Live delivery status |
| 16 | `Switch to order menu` | `bool` | Order menu available |
| 17 | `Price range` | `int` | 1–4 scale (budget → premium) |
| 18 | **`Aggregate rating`** | **`float`** | ⭐ **Primary target — 0.0 to 4.9** |
| 19 | `Rating color` | `str` | Hex/label mapped to rating tier |
| 20 | `Rating text` | `str` | Excellent / Very Good / Good / Average / Poor / Not rated |
| 21 | **`Votes`** | **`int`** | 🗳️ **Total user votes / reviews** |

</details>

<details>
<summary><b>📊 Dataset Quick Stats (click to expand)</b></summary>

<br/>

| Metric | Value |
|--------|------:|
| Total Records | **9,551** |
| Total Features | **21** |
| Countries Represented | **15** |
| Rating Scale | **0.0 – 4.9** |
| Missing Values | **0** ✅ |
| Duplicate Records | **0** ✅ |
| Unrated Restaurants | **2,148 (22.5%)** |
| Rated Restaurants | **7,403 (77.5%)** |
| Max Votes (single restaurant) | **10,934** |
| Avg Votes (all restaurants) | **156.91** |

</details>

---

## 🔬 Analytical Methodology

```
  ┌─────────────────────────────────────────────────────────────────┐
  │   RAW CSV  →  VALIDATION  →  EDA  →  VISUALIZATION  →  INSIGHT  │
  └─────────────────────────────────────────────────────────────────┘

  Step 1 ── Data Ingestion & Integrity Check
           └─ Load CSV · Shape verification · Dtype audit · Null scan

  Step 2 ── Descriptive Statistics Engine
           └─ Mean · Median · Std Dev · Percentiles (ratings + votes)

  Step 3 ── Distribution Analysis
           └─ 25-bin histogram · KDE density (rated-only) · Mean/median lines

  Step 4 ── Categorical Segmentation
           └─ Count per Rating Text label · Share % · Severity sort

  Step 5 ── Range Bucketing & Modal Detection
           └─ pd.cut() → 5 equal bins · identify mode bin · visualize

  Step 6 ── Engagement Analysis
           └─ Votes mean/median overall · per-category average · skew test

  Step 7 ── Cross-Dimensional Synthesis
           └─ Rating × Votes correlation · tier-engagement gradient

  Step 8 ── Executive Summary Dashboard
           └─ ASCII report · all KPIs in single-cell output
```

---

## 📊 Analysis Breakdown

### `Step 1` — Library Setup & Configuration
Import `pandas`, `numpy`, `matplotlib`, `seaborn`, and `scipy`. Set global plot parameters: figure DPI (200), font family, color palettes, and grid style for visual consistency across all 4 charts.

### `Step 2` — Data Loading & Exploration
Load `cognifyz_Dataset_.csv` via `pd.read_csv()`. Confirm shape (9551, 21), inspect dtypes, run `isnull().sum()`, and preview 8 records with analysis-relevant columns only.

### `Step 3` — Descriptive Statistics
Compute full summary statistics for `Aggregate rating` and `Votes`. Output as a formatted boxed table with: count, mean, std, min, 25%, 50%, 75%, max — both for full dataset and rated-only subset.

### `Step 4` — Rating Distribution Visualization
**Two-panel figure:**
- **Left panel:** 25-bin histogram of all 9,551 ratings — tallest bar highlighted in accent color, with vertical mean and median reference lines + annotations
- **Right panel:** KDE density curve restricted to rated restaurants (≥ 2.0), smoothed with Gaussian kernel — reveals the true shape of active restaurant ratings

### `Step 5` — Rating Category Breakdown
**Two-panel figure:**
- **Left panel:** Horizontal bar chart sorted by severity (Excellent → Not Rated), with count labels at end of each bar
- **Right panel:** Donut chart with % share per label, total count in center, legend outside

### `Step 6` — Most Common Rating Range Detection
`pd.cut(df['Aggregate rating'], bins=[0,1,2,3,4,5])` segments all restaurants into 5 equal-width bands. Vertical bar chart with modal bar (3–4) highlighted in contrasting pink. Percentage and count labels above each bar.

### `Step 7` — Votes Engagement Analysis
**Two-panel figure:**
- **Left panel:** Votes histogram clipped to 99th percentile — reveals extreme right-skew; mean and median vertical lines annotated
- **Right panel:** Horizontal bar chart of average votes per rating category — color-coded by severity to show the engagement gradient

### `Step 8` — Executive Summary Dashboard
Single-cell ASCII box output printing all key metrics: rating stats, modal range, votes stats, and category breakdown in a clean, screenshot-ready format for reports and presentations.

---

## 📈 Key Results & Findings

### ⭐ Aggregate Rating Statistics

<div align="center">

| Metric | All Restaurants | Rated Only (≥ 2.0) |
|--------|:--------------:|:------------------:|
| **Count** | 9,551 | 7,403 |
| **Mean** | 2.666 | **3.444** |
| **Median** | 3.200 | 3.300 |
| **Std Deviation** | 1.516 | 0.679 |
| **Minimum** | 0.0 | 2.0 |
| **Maximum** | 4.9 | 4.9 |
| **25th Percentile** | 2.500 | 3.000 |
| **75th Percentile** | 3.700 | 3.900 |

</div>

---

### 🏆 Rating Range Distribution

```
  ╔══════════════════╦══════════════════════╦═════════╗
  ║  Rating Range    ║  Restaurant Count    ║  Share  ║
  ╠══════════════════╬══════════════════════╬═════════╣
  ║  0  –  1         ║        2,148         ║  22.5%  ║  ← Unrated entries
  ║  1  –  2         ║           10         ║   0.1%  ║
  ║  2  –  3         ║        1,891         ║  19.8%  ║
  ║  3  –  4  ★      ║        4,388         ║  46.0%  ║  ← MOST COMMON
  ║  4  –  5         ║        1,114         ║  11.7%  ║
  ╚══════════════════╩══════════════════════╩═════════╝

  🏆  The 3–4 band dominates with 4,388 restaurants — nearly half the entire dataset.
```

---

### 🏅 Rating Category Performance Matrix

<div align="center">

| Tier | Category | Count | Share | Avg Rating | Avg Votes | Engagement Index |
|------|----------|------:|------:|:----------:|----------:|:----------------:|
| 🟢 | **Excellent** | 301 | 3.2% | 4.66 | **851.8** | `████████████████` |
| 🟩 | **Very Good** | 1,079 | 11.3% | 4.17 | **520.5** | `██████████` |
| 🔵 | **Good** | 2,100 | 22.0% | 3.68 | 229.4 | `████` |
| 🟡 | **Average** | 3,737 | 39.1% | 3.05 | 48.2 | `█` |
| 🔴 | **Poor** | 186 | 1.9% | 2.30 | 90.7 | `██` |
| ⚫ | **Not Rated** | 2,148 | 22.5% | 0.00 | 0.9 | `·` |

</div>

---

### 🗳️ Votes Engagement Statistics

<div align="center">

| Metric | Value |
|--------|------:|
| **Mean Votes per Restaurant** | **156.91** |
| **Median Votes** | 31 |
| **Standard Deviation** | 430.17 |
| **25th Percentile** | 5 |
| **75th Percentile** | 131 |
| **99th Percentile** | 2,252 |
| **Maximum (single restaurant)** | 10,934 |
| **Skewness** | +8.3 (extreme right-skew) |

</div>

> ⚠️ **The mean (156.9) is 5× the median (31)** — a power-law distribution where top restaurants absorb the vast majority of all platform votes.

---

## 🧠 Insights & Interpretation

<details open>
<summary><b>💡 Insight 1 — The Unrated Blind Spot</b></summary>

<br/>

**2,148 restaurants (22.5%)** carry a rating of exactly 0.0 — not a poor score, but a complete absence of rating. This inflates the dataset mean to 2.67 when the true mean among actively-rated restaurants is **3.44 — a 29% distortion**.

**Implication:** Any aggregate analysis of "average restaurant quality" that includes unrated entries will be structurally misleading. These must be filtered or treated as a separate segment before drawing quality conclusions.

</details>

<details open>
<summary><b>💡 Insight 2 — The 3–4 Sweet Spot Dominance</b></summary>

<br/>

Nearly **half of all restaurants (46%)** cluster in the 3–4 rating range. This reveals a **platform-wide mediocrity concentration** — the system rewards adequate performance but rarely generates true excellence. Only **15% of restaurants** score 4.0+, and a mere **3.2%** earn "Excellent" status.

**Implication:** A 3.5 rating is not a competitive differentiator — it's the industry floor. Businesses must target 4.0+ to stand out.

</details>

<details open>
<summary><b>💡 Insight 3 — Engagement Follows Quality (With One Anomaly)</b></summary>

<br/>

There is a near-monotonic positive relationship between rating tier and average vote count:

```
  Excellent  →  851.8 avg votes   ██████████████████████████████████ 100%
  Very Good  →  520.5 avg votes   ████████████████████               61%
  Good       →  229.4 avg votes   █████████                          27%
  Average    →   48.2 avg votes   ██                                  6%
  Poor       →   90.7 avg votes   ████                               11%  ← anomaly
  Not Rated  →    0.9 avg votes   ·                                   0%
```

The **Poor category anomaly** (90.7 votes vs. 48.2 for Average) suggests that very poor experiences drive **reactive review behavior** — customers feel compelled to warn others, generating disproportionate engagement despite low quality.

</details>

<details open>
<summary><b>💡 Insight 4 — Power-Law Vote Distribution</b></summary>

<br/>

With mean = 156.9, median = 31, std = 430, and max = 10,934, the votes data follows a **classic power-law (Pareto) distribution**. The top ~1% of restaurants likely account for 30–40% of all votes on the platform.

**Implication:** Median votes (31) is the more honest measure of "typical" engagement. The mean is inflated by a handful of viral, high-visibility restaurants and should not be used as a performance benchmark.

</details>

<details open>
<summary><b>💡 Insight 5 — Excellence Is Exponentially Rewarded</b></summary>

<br/>

The **301 "Excellent" restaurants** (rating ≥ 4.5) average **851.8 votes each** — roughly **17.7× more** than the 3,737 "Average" restaurants at 48.2 votes.

This is not linear growth — it's exponential. The jump from "Good" (229.4) to "Very Good" (520.5) to "Excellent" (851.8) represents compounding returns on quality investment. Being excellent doesn't just attract more customers — it dramatically amplifies platform visibility, review velocity, and social proof.

</details>

---

## 🖼️ Visualizations

<div align="center">

| Chart | File | Description |
|-------|------|-------------|
| **Rating Distribution** | `rating_distribution.png` | Histogram + KDE showing the bimodal shape: spike at 0.0 (unrated) and a bell curve centered around 3.0–3.8 for rated restaurants |
| **Category Breakdown** | `rating_categories.png` | Side-by-side horizontal bar + donut chart revealing that "Average" (39.1%) is the single largest labeled category |
| **Range Bar Chart** | `rating_range.png` | 5-bin bar chart with the dominant 3–4 range highlighted in contrast color — visually communicates the platform's quality distribution at a glance |
| **Votes Analysis** | `votes_analysis.png` | Votes histogram (clipped at 99th pct) revealing extreme right-skew + per-tier engagement bar chart showing the quality-engagement gradient |

</div>

> 📌 All charts rendered at **200 DPI** for high-resolution report embedding. Auto-saved on notebook run.

---

## ⚙️ Setup & Installation

### Prerequisites

```
Python  3.10+
pip     22.0+
git     2.30+
```

### 1 · Clone the Repository

```bash
git clone https://github.com/<your-username>/restaurant-ratings-analysis.git
cd restaurant-ratings-analysis
```

### 2 · Create a Virtual Environment

```bash
# Create
python -m venv venv

# Activate — macOS / Linux
source venv/bin/activate

# Activate — Windows
venv\Scripts\activate
```

### 3 · Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
```

> Or, if a `requirements.txt` is provided:
> ```bash
> pip install -r requirements.txt
> ```

### 4 · Verify Dataset Location

```
✅ cognifyz_Dataset_.csv  →  must be in the same directory as the .ipynb file
```

### 5 · Launch the Notebook

```bash
jupyter notebook Restaurant_Ratings_Analysis.ipynb
```

### 6 · Execute All Cells

```
Jupyter Menu → Kernel → Restart & Run All
```

All 4 output charts will be saved automatically. Estimated runtime: **< 30 seconds**.

---

## 🗂️ Notebook Cell Map

<div align="center">

| Cell | Type | Title | Output |
|:----:|------|-------|--------|
| `01` | Markdown | Task Overview & Dashboard Header | Visual header block |
| `02` | Code | Step 1 — Import Libraries & Configure Styles | ✅ Confirmation message |
| `03` | Code | Step 2 — Load Dataset & Validate | Shape, dtypes, null report, preview |
| `04` | Code | Step 3 — Descriptive Statistics | Formatted stats table |
| `05` | Code | Step 4 — Rating Distribution | `rating_distribution.png` |
| `06` | Code | Step 5 — Category Breakdown | `rating_categories.png` |
| `07` | Code | Step 6 — Most Common Range | `rating_range.png` |
| `08` | Code | Step 7 — Votes Analysis | `votes_analysis.png` |
| `09` | Code | Step 8 — Executive Summary Dashboard | ASCII KPI report |
| `10` | Markdown | Key Insights | Formatted insight blocks |

</div>

---

## 🛠️ Tech Stack

<div align="center">

| Library | Version | Role in This Project |
|---------|:-------:|----------------------|
| **Python** | `3.10+` | Core runtime · data processing · control flow |
| **Pandas** | `2.0+` | CSV ingestion · groupby · `pd.cut()` bucketing · describe() |
| **NumPy** | `1.24+` | Array ops · percentile calculations · numerical precision |
| **Matplotlib** | `3.7+` | Figure/axes creation · multi-panel layouts · DPI export |
| **Seaborn** | `0.12+` | Statistical chart styling · color palettes · KDE plots |
| **SciPy** | `1.10+` | `gaussian_kde` for density curve estimation |
| **Jupyter** | `7.0+` | Interactive notebook environment · cell execution |

</div>

---

## 📜 License & Academic Context

This project was developed for **educational and portfolio purposes** as part of the **Cognifyz Technologies Data Analytics Internship Program**. All analysis, code, visualizations, and written interpretations were produced independently.

<div align="center">

| | |
|--|--|
| 🏢 **Organization** | Cognifyz Technologies |
| 🎓 **Program** | Data Analytics Internship |
| 📁 **Task** | Level 1 · Task 3 · Restaurant Ratings Analysis |
| 🌐 **Website** | [cognifyz.com](https://cognifyz.com) |
| 📧 **Contact** | contact@cognifyz.com |

</div>

---

## 👤 Author

<div align="center">

<br/>

**Karthikeyan Thirunavukkarasu**
*Data Analytics Intern · Cognifyz Technologies*

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/yourprofile)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yourusername)
[![Email](https://img.shields.io/badge/Email-Reach_Out-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your.email@example.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-View_Work-6366f1?style=for-the-badge&logo=vercel&logoColor=white)](https://yourportfolio.com)

<br/>

> *"The goal is to turn data into information, and information into insight." — Carly Fiorina*

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:24243e,50:302b63,100:0f0c29&height=120&section=footer&text=Cognifyz+Technologies+·+Data+Analytics&fontSize=14&fontColor=a78bfa&fontAlignY=65&animation=fadeIn" />

<br/>

![Visitors](https://visitor-badge.laobi.icu/badge?page_id=yourusername.restaurant-ratings-analysis&style=flat-square&color=6366f1)
⭐ **Star this repo if it helped you!**

</div>
