# Happiness, Smoking, and Economic Factors:
## A Cross-Country Analysis

### Overview
This project investigates the relationship between national happiness, smoking prevalence, and economic conditions across countries. By combining three independent international datasets, the analysis explores how lifestyle and economic indicators associate with subjective well-being — with 2022 as the primary year of analysis and a secondary comparison to 2020 (the first year of the COVID-19 pandemic).

### Research Questions
1.	Does GDP per capita predict happiness levels across countries?
2.	Does smoking prevalence have a significant relationship with happiness, after controlling for GDP?
3.	Did the COVID-19 pandemic (2020) alter the relationship between economic conditions and happiness?

### Data Sources
World Happiness Report	worldhappiness.report	2013–2023, country-level happiness index
GDP per Capita	World Bank — World Development Indicators	1960–2024, USD current prices
Smoking Prevalence	Our World in Data / WHO	Age-standardized, adults 15+

Note on year coverage: The smoking dataset provides data every five years (2000, 2005, 2010, 2015, 2020, 2022). After merging all three sources, the overlapping years are 2020 and 2022, yielding 124 countries per year (248 observations total).

### Methodology
The analysis follows a structured data science workflow:
4.	Data loading and inspection from three independent sources
5.	Cleaning and type conversion (including decimal separator normalisation for happiness scores)
6.	Reshaping GDP data from wide to long format
7.	Merging datasets by country and year
8.	Exploratory Data Analysis (EDA) — distributions, scatter plots, correlation heatmap
9.	Outlier analysis using OLS residuals
10.	Regression modelling (simple, multiple, log-transformed)
11.	Hypothesis testing (t-tests, ANOVA)
12.	Pandemic comparison: 2020 vs 2022

### Models
Simple linear regression
Happiness = β₀ + β₁ · GDP + ε
Multiple linear regression
Happiness = β₀ + β₁ · GDP + β₂ · Smoking + ε
Log-transformed GDP (improved fit)
Happiness = β₀ + β₁ · log(GDP) + ε

### Hypotheses Tested
#	Hypothesis	Test
H1	GDP has a significant positive effect on happiness (β₁ > 0)	OLS t-test on β₁
H2	Smoking has no significant effect on happiness (β₂ = 0)	OLS t-test on β₂
H3	High-income countries are significantly happier than low-income countries	Independent t-test + Cohen's d
H4	Mean happiness changed significantly between 2020 and 2022	Paired t-test
H5	Happiness differs across low / middle / high income groups	One-way ANOVA + Tukey HSD

### Key Findings
•	GDP is a strong predictor of happiness — Pearson r = 0.733 (2022), explaining ~54% of cross-country variance in happiness scores
•	Smoking prevalence has a negligible relationship with happiness — r = 0.153, not statistically significant after controlling for GDP
•	The log of GDP fits substantially better than raw GDP, consistent with diminishing returns to income (Easterlin paradox)
•	Outlier countries reveal that non-economic factors (social cohesion, governance, culture) meaningfully influence happiness beyond what income predicts
•	The pandemic did not fundamentally alter the GDP–happiness relationship — correlation was nearly identical in 2020 (r = 0.739) and 2022 (r = 0.733)

### Visualisations
•	Histograms of all three variables
•	Scatter plots: Happiness vs GDP, Happiness vs Smoking, 3-variable plot (colour = smoking)
•	Correlation heatmap
•	Regression plots with 95% confidence bands
•	Residual diagnostic plots (Q-Q, fitted vs residuals, Cook's distance)
•	Outlier annotation plot
•	Side-by-side 2020 vs 2022 comparison

### Limitations
•	Correlation does not imply causation
•	Country-level aggregation may mask within-country inequality
•	Smoking data is only available every five years, limiting temporal analysis
•	Only 124 countries are included after merging — data availability may bias the sample toward wealthier, better-documented countries
•	Unmeasured confounders (education, inequality, institutions) likely affect all three variables

### Project Structure
.
├── Notebook_2022.ipynb     # main analysis notebook
├── data/
│   ├── GDP_PER_CAPITA.csv
│   ├── Smoking_world_.csv
│   └── World_Happiness_2013-2023.csv
└── README.md

### How to Run
# 1. Clone the repository
git clone https://github.com/inatadim/data-science-notebook.git
 
# 2. Navigate to the project folder
cd data-science-notebook
 
# 3. Install dependencies
pip install pandas numpy matplotlib seaborn scipy statsmodels adjustText
 
# 4. Launch Jupyter
jupyter notebook
 
# 5. Open: Notebook_2022.ipynb

Tested with Python 3.11. All dependencies are standard data science libraries.

### Future Improvements
•	Add additional predictors: education index, Gini coefficient, life expectancy, social support scores
•	Expand temporal coverage if smoking data becomes available for more years
•	Apply regularised regression (Ridge/Lasso) to handle multicollinearity when more predictors are added
•	Build an interactive dashboard (Plotly / Streamlit) for country-level exploration


Author: Ina Dimitrova
Final Exam Project — Data Science Course, April 2026
