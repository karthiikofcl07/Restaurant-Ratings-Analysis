<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Playfair+Display&weight=700&size=42&duration=3000&pause=1000&color=E8532A&center=true&vCenter=true&width=700&height=80&lines=Restaurant+Ratings+Analysis;Cognifyz+Data+Analytics" alt="Typing SVG" />

<br/>

```
╔═══════════════════════════════════════════════════════════════╗
║        🍽️  COGNIFYZ TECHNOLOGIES  ·  DATA ANALYTICS          ║
║              Level 1  ·  Task 3  ·  Restaurant Ratings        ║
╚═══════════════════════════════════════════════════════════════╝
```

<br/>

[![Python](https://img.shields.io/badge/Python_3.10+-FFD43B?style=for-the-badge&logo=python&logoColor=black)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter_Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![Pandas](https://img.shields.io/badge/Pandas_2.0-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Seaborn](https://img.shields.io/badge/Seaborn-4EACD8?style=for-the-badge&logo=python&logoColor=white)](https://seaborn.pydata.org)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)](https://matplotlib.org)
[![Status](https://img.shields.io/badge/Status-✅_Completed-2ECC71?style=for-the-badge)](.)

<br/>

> *"Data is the new oil — but only when refined into insight."*

</div>

---

## 📖 Table of Contents

- [🎯 Task Overview](#-task-overview)
- [📂 Project Structure](#-project-structure)
- [📦 Dataset Description](#-dataset-description)
- [🔬 Methodology](#-methodology)
- [📊 Analysis Steps](#-analysis-steps)
- [📈 Key Results & Findings](#-key-results--findings)
- [🧠 Insights & Interpretation](#-insights--interpretation)
- [🖼️ Visualizations](#️-visualizations)
- [⚙️ Setup & Installation](#️-setup--installation)
- [🗂️ Notebook Structure](#️-notebook-structure)
- [🛠️ Tech Stack](#️-tech-stack)
- [📜 License](#-license)
- [👤 Author](#-author)

---

## 🎯 Task Overview

<table>
<tr>
<td width="50%">

### What We're Solving

This analysis dives deep into **restaurant rating data** from Cognifyz Technologies' global restaurant dataset. The task has three precise objectives:

1. **Analyze the distribution** of aggregate ratings across all 9,551 restaurants
2. **Determine the most common rating range** — i.e., which rating band (0–1, 1–2, 2–3, 3–4, 4–5) has the most restaurants
3. **Calculate the average number of votes** received per restaurant and explore how engagement varies by rating tier

</td>
<td width="50%">

### Why It Matters

Understanding rating distributions helps:
- 🔍 **Platform analysts** identify whether ratings skew positive or negative
- 📉 **Business owners** benchmark against industry norms
- 🧑‍💼 **Stakeholders** detect data quality issues (e.g., large unrated proportions)
- 🗳️ **UX designers** understand what drives customer engagement and voting behaviour

</td>
</tr>
</table>

---

## 📂 Project Structure

```
📁 restaurant-ratings-analysis/
│
├── 📓 Restaurant_Ratings_Analysis.ipynb    ← Main analysis notebook (8 steps)
├── 📊 cognifyz_Dataset_.csv                ← Raw dataset (9,551 restaurant records)
│
├── 📁 outputs/
│   ├── 🖼️  rating_distribution.png         ← Histogram + KDE chart
│   ├── 🖼️  rating_categories.png           ← Bar chart + Donut chart
│   ├── 🖼️  rating_range.png                ← Most common range highlight
│   └── 🖼️  votes_analysis.png              ← Votes distribution + per-category avg
│
└── 📄 README.md                            ← This file
```

---

## 📦 Dataset Description

> **Source:** Cognifyz Technologies · Restaurant Intelligence Dataset

| Field | Type | Description |
|-------|------|-------------|
| `Restaurant ID` | Integer | Unique identifier |
| `Restaurant Name` | String | Name of the restaurant |
| `Country Code` | Integer | Numeric country identifier |
| `City` | String | City of the restaurant |
| `Cuisines` | String | Comma-separated cuisine types |
| `Average Cost for two` | Integer | Estimated cost for two people |
| `Currency` | String | Local currency name |
| `Has Table booking` | Boolean | Whether bookings are accepted |
| `Has Online delivery` | Boolean | Whether delivery is available |
| `Price range` | Integer | 1–4 scale (budget → luxury) |
| **`Aggregate rating`** | **Float** | **Main analysis target (0.0 – 4.9)** |
| `Rating color` | String | Colour code mapped to rating tier |
| `Rating text` | String | Label: Excellent / Very Good / Good / Average / Poor / Not rated |
| **`Votes`** | **Integer** | **Number of user votes/reviews** |

<details>
<summary><b>📊 Quick Dataset Stats (click to expand)</b></summary>

<br/>

| Metric | Value |
|--------|-------|
| Total Records | **9,551** |
| Total Columns | **21** |
| Countries Represented | **15** |
| Rating Scale | **0.0 – 4.9** |
| Missing Values | **0** (clean dataset) |
| Unrated Restaurants | **2,148 (22.5%)** |

</details>

---

## 🔬 Methodology

```
Raw CSV Data
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  Step 1 · Data Ingestion & Validation                   │
│  → Load CSV, check shape, verify dtypes, null check     │
└─────────────────────────────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  Step 2 · Descriptive Statistics                        │
│  → Mean, Median, Std Dev, Min/Max, Percentiles          │
└─────────────────────────────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  Step 3 · Distribution Analysis                         │
│  → Histogram, KDE (rated only), Mean/Median overlay     │
└─────────────────────────────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  Step 4 · Categorical Breakdown                         │
│  → Count & share per Rating Text category               │
└─────────────────────────────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  Step 5 · Range Bucketing & Mode Detection              │
│  → pd.cut into 5 bins, identify modal bin               │
└─────────────────────────────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  Step 6 · Votes Engagement Analysis                     │
│  → Mean/Median votes overall & by rating category       │
└─────────────────────────────────────────────────────────┘
     │
     ▼
Final Summary Dashboard · Insights Report
```

---

## 📊 Analysis Steps

### Step 1 — Library Setup & Configuration
Import `pandas`, `numpy`, `matplotlib`, `seaborn`, and `scipy`. Configure global plot styles, DPI, and color palettes for consistent visual output.

### Step 2 — Data Loading & Exploration
Load the CSV, inspect shape, data types, and null values. Preview the first 8 records with a filtered column view showing only analysis-relevant fields.

### Step 3 — Descriptive Statistics
Generate a formatted statistics table covering `count`, `mean`, `std`, `min`, `25%`, `50%`, `75%`, and `max` — both for ratings and votes. Displayed as a clean boxed console output.

### Step 4 — Rating Distribution Visualization
A **two-panel chart** containing:
- Left: Histogram of all ratings (25 bins), with the peak bar highlighted and mean/median vertical lines
- Right: KDE density plot restricted to rated restaurants only (excluding zeros)

### Step 5 — Rating Category Breakdown
A **two-panel chart** containing:
- Left: Horizontal bar chart sorted by category severity with count labels
- Right: Donut chart showing percentage share per category, with total count in centre

### Step 6 — Most Common Rating Range
`pd.cut()` bins all ratings into five equal ranges (0–1, 1–2, 2–3, 3–4, 4–5). A vertical bar chart highlights the modal range in a contrasting colour, with count labels above each bar.

### Step 7 — Votes Analysis
A **two-panel chart** containing:
- Left: Histogram of votes (clipped to 99th percentile) with mean and median lines
- Right: Bar chart of average votes by rating category (colour-coded by category severity)

### Step 8 — Final Summary Dashboard
A formatted ASCII box table printing all key results in one clean, readable block. Used as the final cell output for easy screenshot/reporting.

---

## 📈 Key Results & Findings

### ⭐ Aggregate Rating Statistics

| Metric | All Restaurants | Rated Only (excl. 0) |
|--------|:--------------:|:-------------------:|
| **Count** | 9,551 | 7,403 |
| **Mean** | 2.666 | **3.444** |
| **Median** | 3.20 | 3.30 |
| **Std Dev** | 1.516 | 0.679 |
| **Min** | 0.0 | 2.0 |
| **Max** | 4.9 | 4.9 |

---

### 🏆 Most Common Rating Range

```
  Rating Range  │  Restaurant Count  │  Share
  ──────────────┼────────────────────┼───────
  0  –  1       │       2,148        │  22.5%   ← Unrated entries
  1  –  2       │          10        │   0.1%
  2  –  3       │       1,891        │  19.8%
  3  –  4       │       4,388        │  46.0%   ★ MOST COMMON
  4  –  5       │       1,114        │  11.7%
```

> 🏆 **The 3–4 range is the most common**, containing **4,388 restaurants (46%)** of the entire dataset.

---

### 🏅 Rating Category Breakdown

| Category | Count | Share | Avg Rating | Avg Votes |
|----------|------:|------:|:----------:|----------:|
| 🟢 Excellent | 301 | 3.2% | 4.66 | **851.8** |
| 🟩 Very Good | 1,079 | 11.3% | 4.17 | **520.5** |
| 🔵 Good | 2,100 | 22.0% | 3.68 | 229.4 |
| 🟡 Average | 3,737 | 39.1% | 3.05 | 48.2 |
| 🔴 Poor | 186 | 1.9% | 2.30 | 90.7 |
| ⚫ Not Rated | 2,148 | 22.5% | 0.00 | 0.9 |

---

### 🗳️ Votes Statistics

| Metric | Value |
|--------|------:|
| **Average Votes per Restaurant** | **156.91** |
| Median Votes | 31 |
| Standard Deviation | 430.17 |
| 25th Percentile | 5 |
| 75th Percentile | 131 |
| Maximum (single restaurant) | **10,934** |

> ⚠️ The votes distribution is **heavily right-skewed** — the mean (156.9) is ~5× the median (31), meaning a small number of popular restaurants receive the bulk of all votes.

---

## 🧠 Insights & Interpretation

<details open>
<summary><b>💡 Insight 1 — The Unrated Problem</b></summary>

**22.5% of restaurants (2,148)** have never been rated. This inflates the "Not Rated" category and depresses the overall dataset mean to 2.67 when the true mean of rated restaurants is 3.44. Any platform-wide analysis must account for or filter these null-equivalent entries.

</details>

<details open>
<summary><b>💡 Insight 2 — The 3–4 Sweet Spot</b></summary>

Nearly **half of all restaurants (46%)** fall in the 3–4 rating range, and 39% of restaurants carry the "Average" label. The platform leans toward mediocre ratings — true excellence (4+) represents only **15% of all restaurants**, and only **3.2%** are rated "Excellent."

</details>

<details open>
<summary><b>💡 Insight 3 — Engagement Follows Quality</b></summary>

There is a **near-perfect positive correlation between rating tier and average votes**:

```
Excellent  →  851.8 votes avg  ████████████████████████████████
Very Good  →  520.5 votes avg  ████████████████████
Good       →  229.4 votes avg  █████████
Average    →   48.2 votes avg  ██
Poor       →   90.7 votes avg  ███  (anomaly: poor experiences drive reviews)
Not Rated  →    0.9 votes avg  ·
```

Higher-rated restaurants attract dramatically more votes — likely because people actively seek out and review great experiences, while very poor ones also drive reactive reviews.

</details>

<details open>
<summary><b>💡 Insight 4 — Vote Distribution is Power-Law</b></summary>

With a mean of 156.9 but a median of only 31, and a standard deviation of 430, the votes data follows a **power-law (long-tail) distribution**. The top 1% of restaurants likely account for a disproportionate share of all votes on the platform.

</details>

<details open>
<summary><b>💡 Insight 5 — The Rare Excellent</b></summary>

Only **301 restaurants** (3.2%) achieved "Excellent" status (rating ≥ 4.5). These restaurants average **851.8 votes** — roughly **17× more than "Average" restaurants**. Being truly excellent is both rare and highly rewarded in terms of user engagement.

</details>

---

## 🖼️ Visualizations

| Preview | Chart Description |
|---------|------------------|
| `rating_distribution.png` | **Histogram + KDE** — Shows the bimodal distribution caused by unrated (0) restaurants and the cluster of rated restaurants around 3.0–3.8 |
| `rating_categories.png` | **Horizontal Bar + Donut** — Side-by-side comparison of count and percentage share per rating label |
| `rating_range.png` | **Range Bar Chart** — Highlights the dominant 3–4 range in contrasting pink against all other bands |
| `votes_analysis.png` | **Votes Histogram + Category Bar** — Reveals the extreme skew of the votes distribution and the tier-based engagement gradient |

---

## ⚙️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/restaurant-ratings-analysis.git
cd restaurant-ratings-analysis
```

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate           # Windows
```

### 3. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
```

Or use the requirements file if provided:

```bash
pip install -r requirements.txt
```

### 4. Launch the Notebook

```bash
jupyter notebook Restaurant_Ratings_Analysis.ipynb
```

> ⚠️ **Important:** Ensure `cognifyz_Dataset_.csv` is in the **same directory** as the `.ipynb` file before running.

### 5. Run All Cells

In Jupyter: `Kernel → Restart & Run All` — all 4 charts will be saved automatically to the current directory.

---

## 🗂️ Notebook Structure

| # | Cell Type | Title | Key Output |
|---|-----------|-------|------------|
| 1 | `Markdown` | Task Overview & Objectives | Header, goals, dataset summary |
| 2 | `Code` | Step 1 — Import Libraries | Confirmation message |
| 3 | `Code` | Step 2 — Load & Explore Dataset | Shape, columns, head preview |
| 4 | `Code` | Step 3 — Descriptive Statistics | Boxed stats table |
| 5 | `Code` | Step 4 — Rating Distribution | `rating_distribution.png` |
| 6 | `Code` | Step 5 — Category Breakdown | `rating_categories.png` |
| 7 | `Code` | Step 6 — Most Common Range | `rating_range.png` |
| 8 | `Code` | Step 7 — Votes Analysis | `votes_analysis.png` |
| 9 | `Code` | Step 8 — Final Summary Dashboard | ASCII results table |
| 10 | `Markdown` | Key Insights | Formatted insight table |

---

## 🛠️ Tech Stack

| Library | Version | Role |
|---------|---------|------|
| **Python** | 3.10+ | Core language |
| **Pandas** | 2.0+ | Data loading, cleaning, groupby, cut |
| **NumPy** | 1.24+ | Numerical arrays and operations |
| **Matplotlib** | 3.7+ | All chart rendering, figure layout |
| **Seaborn** | 0.12+ | Statistical styling and palette |
| **SciPy** | 1.10+ | `gaussian_kde` for density estimation |
| **Jupyter** | 7.0+ | Interactive notebook environment |

---

## 📜 License

This project is developed for **educational purposes** as part of the **Cognifyz Technologies Data Analytics Internship Program**. All analysis, code, and visualizations were produced independently.

> 🏢 **Cognifyz Technologies** — AI · Machine Learning · Data Analytics  
> 🌐 [cognifyz.com](https://cognifyz.com) · 📧 contact@cognifyz.com

---

## 👤 Author

<div align="center">

**Karthikeyan Thirunavukkarasu**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/yourprofile)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yourusername)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your.email@example.com)

</div>

---

<div align="center">

```
   ·  Cognifyz Data Analytics Internship
```

⭐ *If this project helped you, consider giving it a star!*

</div>
