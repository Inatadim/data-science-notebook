# Happiness, Smoking, and Economic Factors: A Cross-Country Analysis

## Overview
This project investigates the relationship between happiness levels, smoking prevalence, and economic conditions across countries.

By combining multiple international datasets, the analysis explores how both lifestyle factors and economic indicators are associated with subjective well-being.

## Research Questions
- What is the relationship between smoking prevalence and happiness across countries?
- How does GDP per capita relate to happiness levels?
- To what extent do smoking prevalence and GDP per capita jointly explain variations in happiness across countries?

## Data Sources
The project integrates data from three independent sources:

- World Happiness Report — provides country-level happiness scores
- World Bank — GDP per capita (economic indicator)
- Our World in Data — smoking prevalence (% of population)

## Methodology
The analysis follows a structured data science workflow:

1. Data collection from multiple independent sources  
2. Data cleaning and preprocessing  
3. Standardization of country names and formats  
4. Merging datasets by country and year  
5. Exploratory Data Analysis (EDA)  
6. Correlation analysis  
7. Linear regression modeling  

## Model
Happiness is modeled as a function of smoking prevalence and GDP per capita:

Happiness = β₀ + β₁ · Smoking + β₂ · GDP + ε

## 📊 Visualizations
The project includes:
- Scatter plots (Happiness vs GDP, Happiness vs Smoking)
- Correlation heatmap
- Distribution plots
- Regression analysis outputs

## Key Findings
- GDP per capita shows a strong positive relationship with happiness
- Smoking prevalence shows a weaker and generally negative relationship with happiness
- Economic factors appear to be stronger predictors of happiness than smoking behavior

## Limitations
- Correlation does not imply causation  
- Cultural and social factors are not included  
- Data is aggregated at the country level  
- Some datasets may not align perfectly by year  

## Project Structure
- `notebook.ipynb` — main analysis and modeling  
- `data/` — datasets used in the project  
- `README.md` — project documentation  

## How to Run
1.	Clone the repository: git clone https://github.com/inatadim/data-science-notebook.git
2.	Navigate to the folder: cd data-science-notebook
3.	Start Jupyter: jupyter notebook
4.	Open: Alcohol.ipynb
________________________________________
Future Improvements • Add more variables (education, health, life expectancy) • Apply regression or machine learning models • Improve statistical testing • Expand dataset coverage
________________________________________
Author Ina Dimitrova
