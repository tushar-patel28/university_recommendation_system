# Scripts Directory

This directory contains the R analysis script for the university recommendation system.

## Main Script

**File**: `Inof6105_final_college analysis_recommendation.r`  
**Lines**: ~793 lines of code  
**Language**: R (version 4.0+)

### Script Overview

The script is organized into two major parts:

#### Part 1: Comprehensive Data Analysis
1. **Data Import & Cleaning** - Loads and preprocesses the college dataset
2. **Feature Engineering** - Creates derived variables and classifications
3. **Exploratory Analysis** - Interactive Plotly visualizations
4. **Cluster Analysis** - K-means clustering (k=4)
5. **Regression Modeling** - Predicts student-to-employee ratios
6. **Integrated Analysis** - Combines insights from all methods

#### Part 2: Interactive Recommendation System
- Custom recommendation function
- Shiny web application with filters
- Interactive data tables
- Real-time university matching

### Required R Packages

```r
# Data manipulation
tidyverse, dplyr, readxl

# Visualization  
plotly, ggplot2, viridis, corrplot, factoextra

# Machine learning
cluster, caret, leaps, car

# Web application
shiny, DT

# Other utilities
maps, reshape2
```

### How to Run

```r
# Set working directory to project root
setwd("path/to/university_recommendation_system")

# Source the script
source("scripts/Inof6105_final_college analysis_recommendation.r")
```

### Script Outputs

When executed, the script produces:

1. **13 Interactive Visualizations** (saved to `outputs/` directory)
   - Pie charts, bar charts, box plots
   - Choropleth maps
   - 3D cluster visualizations
   - Correlation heatmaps
   - Variable importance plots

2. **Statistical Results** (printed to console)
   - Cluster summaries
   - Regression coefficients
   - Model performance metrics
   - Key findings by institution type and region

3. **Recommendation Function** (loaded into R environment)
   - `recommend_universities()` - ready to use

4. **Shiny App** (optional)
   - Interactive web interface for recommendations

### Key Functions

**Main Recommendation Function**:
```r
recommend_universities(
  state = NULL,              # Filter by state(s)
  size_category = NULL,      # "Small", "Medium", "Large"
  has_housing = NULL,        # "Yes" or "No"
  support_level = NULL,      # "High", "Medium", "Low"
  top_n = 10                 # Number of results
)
```

### Analysis Methods

- **K-means Clustering**: Identifies 4 institutional profiles
- **Stepwise Regression**: Feature selection for predictive model
- **Cross-validation**: 10-fold CV for model validation
- **Correlation Analysis**: Explores variable relationships
- **Geographic Analysis**: State and region comparisons

### Customization

To modify the analysis:

1. **Change cluster number**: Edit `k_optimal <- 4` 
2. **Adjust filters**: Modify Shiny UI inputs
3. **Add visualizations**: Use Plotly syntax
4. **New features**: Add to feature engineering section

### Performance Notes

- Runtime: ~5-10 minutes on typical hardware
- Memory: Requires ~2-4 GB RAM
- Interactive plots: Best viewed in RStudio or web browser

## Troubleshooting

**Common Issues**:

- **Missing packages**: Run `install.packages(c("tidyverse", "plotly", ...))`
- **Data file not found**: Ensure `data/us-colleges-and-universities.xlsx` exists
- **Shiny app won't launch**: Uncomment `shinyApp(ui = ui, server = server)` at end of script
- **Plots not displaying**: Check that you're viewing in RStudio or saving to files

## Citation

If you use this analysis in your research, please cite:

```
Patel, T. V. (2024). University Recommendation System: 
Data-Driven Analysis of US Colleges and Universities. 
INFO6105 Final Project, Northeastern University.
```
