# 🌾 Seasonal Agriculture Performance Analysis

**VOIS AICTE Batch 1 (2026–2027) — Major Project**

A data analytics project investigating how agricultural performance in India varies across the three cropping seasons — **Kharif, Rabi, and Zaid** — using exploratory data analysis, statistical testing, and visualization.

> **Student:** Ashish Sharma
> **College:** Chandigarh University
> **AICTE Student ID:** STU69e8ccaff3a6c1776864431

---

## 📌 Problem Statement

Agricultural activities are influenced by seasonal variations in environmental conditions, farming practices, resource availability, and market conditions. As a result, agricultural performance may differ from one season to another. However, raw agricultural data does not clearly explain how performance changes across seasons or what patterns can be observed under different seasonal conditions.

This project analyzes a seasonal agriculture dataset to uncover meaningful patterns, trends, relationships, and variations in performance across Kharif, Rabi, and Zaid seasons.

## 🎯 Objectives

- Explore and understand the dataset
- Clean and prepare the data for analysis (handle missing values, duplicates, outliers)
- Examine how agricultural performance varies across seasons
- Identify important seasonal patterns and trends
- Investigate relationships between seasonal environmental conditions and agricultural outcomes
- Compare performance across crops, states, and irrigation methods
- Apply statistical testing (one-way ANOVA) to validate seasonal differences
- Derive evidence-based conclusions and recommendations

## 👥 End Users

| User Group | How They Benefit |
|---|---|
| Farmers & agricultural cooperatives | Plan crop planting and irrigation choices by season |
| State agriculture departments & policymakers | Design season-specific advisory and subsidy programs |
| Agri-fintech companies & crop insurance providers | Assess seasonal risk to design loans and insurance plans |
| Researchers & students | Study seasonal farming trends in yield, weather, and prices |

## 🗂️ Dataset

`seasonal_agriculture_performance_dataset.csv` — **4,000 farm records × 28 columns**, covering Indian **states, districts, and crop types**, spanning the Kharif, Rabi, and Zaid seasons, with the following categories of features:

- **Environmental conditions:** rainfall, temperature, humidity, sunlight hours, soil pH, soil moisture
- **Farming practices:** irrigation method, fertilizer use (N/P/K), pesticide use, seed quality score
- **Performance outcomes:** yield (t/ha), production (tonnes), total cost, revenue, profit, water efficiency, disease/pest risk

## 🧪 Methodology

The analysis follows a standard data science workflow:

1. **Data Understanding** — inspect structure, data types, and summary statistics
2. **Data Cleaning & Preparation**
   - Imputed missing values (Rainfall, Soil Moisture, Yield) using **season-wise median**
   - Checked and removed duplicate rows
   - Detected and capped outliers using the **IQR method** (winsorization on Yield)
   - Engineered new features: `Profit_Margin_pct`, `Cost_per_Tonne`
3. **Univariate Analysis** — distribution of key numeric and categorical variables
4. **Bivariate Analysis** — Yield/Profit vs. Season, Water Used vs. Yield
5. **Statistical Testing** — one-way **ANOVA** to test whether seasonal differences in yield are statistically significant
6. **Multivariate Analysis** — correlation heatmaps and multi-variable pairplots (Rainfall, Temperature, Yield, Season)
7. **Custom/Student-Designed Analyses:**
   - Crop performance within each season (Crop × Season yield heatmap)
   - Regional consistency of seasonal patterns (State × Season profit heatmap)
   - Irrigation method effectiveness by season
8. **Outlier / Anomaly Detection** — high-input/low-yield farms, high-risk/loss-making farms
9. **Summary & Conclusions** — season-wise performance summary and data-driven recommendations

## ❓ Key Analytical Questions

1. How does agricultural performance (yield, profit) vary across seasons?
2. How do environmental conditions (rainfall, temperature, humidity, sunlight) differ by season?
3. How does resource usage (fertilizer, pesticide, water) vary across seasons?
4. How do economic outcomes (cost, revenue, profit margin) vary by season?
5. How does disease/pest risk vary across seasons?
6. Which crops and states show consistent vs. season-dependent performance?
7. Which irrigation method is most effective in each season?

## 📊 Key Findings

- Kharif, Rabi, and Zaid show measurably different average yield, profit, and resource-efficiency profiles — the ANOVA test confirms this seasonal difference in yield is **statistically significant**.
- Environmental conditions vary systematically by season and track with seasonal shifts in yield and disease/pest risk.
- **Drip irrigation** shows a consistent water-efficiency edge over flood/rainfed methods across all seasons.
- A meaningful share of farms in *every* season report negative profit — cost overruns are not confined to a single season.
- Crop × Season and State × Season heatmaps reveal that not all crops/regions follow the same seasonal pattern — some are stable across seasons, others are highly season-dependent.
- High fertilizer/pesticide use does **not** guarantee higher yield; a subset of farms show heavy input use paired with below-median yield (inefficiency rather than resource scarcity).
- Yield and Profit distributions are right-skewed, so medians give a more representative picture than means alone.
- No single environmental/input variable strongly correlates with Yield in isolation (|r| < 0.15) — performance is driven by a **combination** of conditions, which is why multivariate and seasonal-comparison views matter more than single correlations.

**Recommendations:**
- Prioritize drip irrigation in seasons/regions with the lowest water efficiency.
- Target agronomic support (soil testing, seed quality checks) at the lowest-yielding crop-season combinations.
- Investigate loss-making farm segments per season for cost-control opportunities.
- Plan preventive interventions ahead of the highest disease/pest-risk season.
- Replicate best-performing states' seasonal practices in lower-performing states growing the same crop.

**Limitations:** The analysis uses a single cross-sectional dataset (no multi-year trend); missing-value imputation and outlier capping were done at the season level. Findings should be validated against multi-year data before large-scale policy application.

## 🛠️ Technology Used

- **Python** — Pandas, NumPy (data cleaning & analysis)
- **Matplotlib**, **Seaborn** (data visualization)
- **SciPy** (statistical testing — one-way ANOVA)
- **Jupyter Notebook** (development environment)

## 📁 Repository Structure

```
├── Seasonal_Agriculture_Performance_Analysis.ipynb   # Main analysis notebook
├── seasonal_agriculture_performance_dataset.csv      # Dataset (4,000 records × 28 columns)
├── imgs/                                              # Saved plots/figures generated by the notebook
├── Major_Project_Seasonal_Agriculture_Performance_Analysis.pdf   # Project brief/problem statement
├── VOIS_Major_Project_PPT_Submission_Template.pptx    # Project presentation
└── README.md
```

## 🚀 How to Run

1. Clone the repository:
```bash
   git clone https://github.com/ashish8847/VOIS-AICTE-DATA-ANALYTICS--Major-Project-Seasonal-Agriculture-Performance-Analysis.git
   cd VOIS-AICTE-DATA-ANALYTICS--Major-Project-Seasonal-Agriculture-Performance-Analysis
```
2. Install dependencies:
```bash
   pip install pandas numpy matplotlib seaborn scipy jupyter
```
3. Make sure `seasonal_agriculture_performance_dataset.csv` is in the project root, and that an `imgs/` folder exists for saved plots.
4. Launch the notebook:
```bash
   jupyter notebook Seasonal_Agriculture_Performance_Analysis.ipynb
```
5. Run all cells from top to bottom.

## 🔮 Future Scope

- **Yield Prediction** — ML models such as Random Forest, XGBoost, or Gradient Boosting
- **Profit Prediction** — model expected profit / profit margin
- **Crop Recommendation System** — suggest the most suitable crop for a given season and region
- **Smart Irrigation Recommendation** — extend the Drip/Flood/Rainfed/Sprinkler comparison into a recommendation system
- **Disease & Pest Risk Prediction** — classification/regression model for risk prediction

## 📄 Project Deliverables

- 📓 Jupyter Notebook — full analysis with code, visualizations, and interpretation
- 📊 PPT Presentation — project summary for submission
- 📃 Project Brief (PDF) — original problem statement provided by VOIS/AICTE
- 📁 Dataset (CSV) — seasonal_agriculture_performance_dataset.csv, 4,000 records × 28 columns

## 🎓 Course Completion

This project was completed as part of the **VOIS for Tech Program on Data Analytics**, Batch 1 (2026–2027).

---
