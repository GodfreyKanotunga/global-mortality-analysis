# Global Mortality Patterns and Country Clustering (2010–2019)

**Godfrey M. Kanotunga · Isabel T. Mhike** | Applied Data Science · Clarkson University | IA650 Data Mining

A data-driven analysis of global causes of death across 192 countries from 2010 to 2019, using PCA, K-means clustering, and supervised machine learning to identify mortality patterns and country profiles.

> 📄 **[⬇ Download Research Paper (PDF)](./20260401_Isabel_Godfrey_IA650%20(4).pdf)**

---

## 🔗 Live Dashboard

**[🔗 View Interactive Dashboard](https://godfreykanotunga.github.io/global-mortality-analysis/mortality_dashboard.html)**

---

## Key Findings

- Global **total deaths rose** from 49.1M (2010) to 53.1M (2019), while the **average death rate declined** from 777 to 747 per 100k — driven by population growth, not worsening health
- **Cardiovascular diseases** are the leading cause of death globally (168M deaths, 33% of total)
- **High-income countries** show chronic disease dominance; **low-income countries** retain high infectious and maternal-neonatal burdens
- **PCA** identified two dominant mortality dimensions: infectious/vulnerability burden (PC1: 39.3%) and chronic/lifestyle burden (PC2: 15.1%)
- **K-means clustering** produced 3 interpretable country profiles: High Vulnerability, High Chronic, and Transition/Mixed
- **Random Forest Classification** achieved **98.4% accuracy** (F1 = 0.98) predicting cluster membership

---

## Methods

| Step | Method |
|---|---|
| Data cleaning | Missing value checks, duplicate detection, population validation |
| Standardization | Cause-specific death rates per 100,000 population |
| Transformation | log(1+x) applied to right-skewed rate variables |
| EDA | Global trends, leading causes, income group comparisons, correlation heatmap |
| Dimension reduction | PCA on standardized log-transformed rates |
| Clustering | K-means (k=3) in PCA space, elbow method for k selection |
| Geographic mapping | Country cluster distribution by mortality profile |
| Supervised learning | Linear Regression, RF Regression, RF Classification |

---

## Model Results

| Model | Task | RMSE | R² | Accuracy | Macro F1 |
|---|---|---|---|---|---|
| **Random Forest Classification** | Cluster prediction | — | — | **98.4%** | **0.98** |
| Random Forest Regression | CVD rate prediction | 47.23 | 0.93 | — | — |
| Linear Regression | CVD rate prediction | 133.70 | 0.44 | — | — |

---

## Dataset

1,920 observations × 38 variables. Each row = one country-year combination (2010–2019).

Key variables: country, income group, population, year, age 65+%, dependency ratio, total deaths, death rate per 100k, and 32 cause-specific death counts.

**Sources:**
- Population & age data: [Our World in Data](https://ourworldindata.org/grapher/population-by-age-group?overlay=download-data)
- Disease dataset: [Kaggle — Cause of Deaths Around the World](https://www.kaggle.com/datasets/iamsouravbanerjee/cause-of-deaths-around-the-world)
- Income classification: [World Bank Country Lending Groups](https://datahelpdesk.worldbank.org/knowledgebase/articles/906519-world-bank-country-and-lending-groups)

---

## Tools

`Python` · `pandas` · `scikit-learn` · `matplotlib` · `seaborn` · `Chart.js`

---

## Files

```
global-mortality-analysis/
├── mortality_dashboard.html          # Interactive web dashboard
├── cleaned_cause_of_death_with_income.xlsx  # Dataset
├── Global_Mortality_Analysis_Paper.pdf      # Research paper
└── README.md
```

---

## Authors

- **Godfrey M. Kanotunga** — kanotugm@clarkson.edu
- **Isabel T. Mhike** — mhikei@clarkson.edu

Applied Data Science Program · Clarkson University · Potsdam, NY
