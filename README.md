# IPM Analysis Rstudio
# Indonesian Human Development Index (HDI) Statistical Analysis

A comprehensive statistical analysis project examining the factors influencing life expectancy in Indonesia using multiple regression techniques including OLS, Best Subset Regression, and Stepwise Selection.

## 📊 Project Overview

This project analyzes the Indonesian Human Development Index (HDI) dataset from 2021 to identify key factors that influence life expectancy across different regions. The analysis employs various statistical modeling techniques to understand the relationships between socioeconomic indicators and life expectancy outcomes.

## 🎯 Objectives

- Analyze the relationship between life expectancy and various socioeconomic factors
- Apply multiple regression modeling techniques (OLS, Best Subset, Stepwise)
- Handle missing values and outliers in the dataset
- Identify the most significant predictors of life expectancy
- Compare different model selection approaches

## 📋 Dataset Description

The dataset contains socioeconomic indicators for Indonesian regions in 2021, including:

- **Life Expectancy** (Target variable) - Average life expectancy in years
- **Poverty Rate** (`perc_Po`) - Percentage of population below poverty line
- **Education** (`avgschool`) - Average years of schooling for population 15+
- **Per Capita Spending** (`spendpercap`) - Adjusted per capita expenditure (IDR thousands/person/year)
- **HDI Score** (`ipm`) - Human Development Index score
- **Sanitation Access** (`perc_san`) - Percentage of households with proper sanitation
- **Clean Water Access** (`perc_dr`) - Percentage of households with clean drinking water
- **Unemployment Rate** (`unemploy`) - Open unemployment rate
- **Labor Participation** (`labor_part`) - Labor force participation rate
- **Regional GDP** (`pdrb`) - Gross Regional Domestic Product (constant prices)

## 🛠️ Technologies Used

### R Environment
- **R** (version 4.x recommended)
- **RStudio** or R Markdown environment

### Required R Packages
```r
# Data manipulation and visualization
library(dplyr)
library(ggplot2)
library(GGally)
library(tidyr)
library(tidyverse)

# Statistical analysis
library(corrplot)
library(car)
library(MASS)
library(leaps)
library(caret)

# Missing data handling
library(naniar)
```

## 🚀 Getting Started

### Prerequisites

1. **R Installation**: Download and install R from [CRAN](https://cran.r-project.org/)
2. **RStudio**: Download RStudio from [RStudio website](https://www.rstudio.com/)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/indonesian-hdi-analysis.git
cd indonesian-hdi-analysis
```

2. Install required R packages:
```r
# Run this in R console
install.packages(c("ggplot2", "GGally", "dplyr", "corrplot", 
                   "naniar", "tidyr", "tidyverse", "caret", 
                   "leaps", "car", "MASS"))
```

3. Set working directory:
```r
setwd("path/to/your/project/directory")
```

4. Place the dataset file `ipm-indonesia2021-cluster.csv` in your working directory

### Running the Analysis

1. Open `PA OLS.Rmd` in RStudio
2. Run the chunks sequentially or knit the entire document
3. Results will be generated as HTML notebook output

## 📁 Project Structure

```
indonesian-hdi-analysis/
├── PA OLS.Rmd                    # Main analysis R Markdown file
├── ipm-indonesia2021-cluster.csv # Dataset file
├── README.md                     # Project documentation
└── output/                       # Generated plots and results
```

## 🔍 Analysis Workflow

### 1. Data Import and Preprocessing
- Load and inspect the dataset
- Rename variables for clarity
- Handle missing values using complete case analysis

### 2. Exploratory Data Analysis (EDA)
- **Scatter Plot Matrix**: Visualize relationships between variables
- **Correlation Analysis**: Identify linear relationships using correlation heatmaps
- **Distribution Analysis**: Examine data distributions using density plots
- **Outlier Detection**: Use boxplots to identify outliers

### 3. Data Normalization
- **Outlier Treatment**: Apply IQR capping method to handle extreme values
- **Data Transformation**: Create capped versions of variables with outliers

### 4. Statistical Modeling

#### Ordinary Least Squares (OLS)
- Fit multiple linear regression models
- Compare original vs. outlier-capped data
- Assess multicollinearity using Variance Inflation Factor (VIF)

#### Best Subset Regression
- Evaluate all possible variable combinations
- Use selection criteria: Adjusted R², Cp, BIC, RSS
- Identify optimal number of predictors

#### Stepwise Selection
- **Backward Selection**: Start with all variables, remove non-significant ones
- **Forward Selection**: Start with intercept, add significant variables
- Compare AIC values for model selection

## 📈 Key Findings

The analysis reveals important insights about factors affecting life expectancy in Indonesia:

1. **Significant Predictors**: Education level, HDI score, and poverty rate show strong associations with life expectancy
2. **Model Performance**: Stepwise regression identifies the most parsimonious model
3. **Outlier Impact**: Outlier treatment improves model stability and interpretability

## 🎯 Model Evaluation Metrics

- **R-squared**: Proportion of variance explained
- **Adjusted R-squared**: Accounts for number of predictors
- **AIC/BIC**: Information criteria for model comparison
- **VIF**: Multicollinearity assessment
- **Residual Analysis**: Model assumptions validation

## 📊 Visualization Outputs

The analysis generates various visualizations:
- Correlation heatmaps
- Scatter plot matrices
- Density plots for variable distributions
- Before/after boxplots for outlier treatment
- Model diagnostic plots

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/analysis-improvement`)
3. Commit your changes (`git commit -am 'Add new analysis technique'`)
4. Push to the branch (`git push origin feature/analysis-improvement`)
5. Create a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Your Name** - *Initial work* - [YourGitHub](https://github.com/yourusername)

## 🙏 Acknowledgments

- Indonesian Central Bureau of Statistics (BPS) for providing the HDI dataset
- R Community for excellent statistical packages
- Academic supervisors and colleagues for guidance

## 📞 Support

If you encounter any issues or have questions:
- Open an issue on GitHub
- Contact: your.email@example.com

## 📚 References

- Indonesian Central Bureau of Statistics (BPS)
- R Documentation for statistical packages
- Academic literature on HDI analysis and regression modeling

---

**Note**: This analysis is for educational and research purposes. Results should be interpreted within the context of the dataset's limitations and the specific time period (2021) of the study.
