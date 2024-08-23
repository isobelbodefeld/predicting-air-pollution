# Predicting Ambient Air Pollution Concentrations Across the Continental US

## Overview

This project aims to predict ambient air pollution concentrations (specifically PM2.5 levels) across the continental United States using various statistical and machine learning models. The models used include Linear Regression, k-Nearest Neighbors (kNN), and Random Forest. Each model was chosen for its strengths in handling different aspects of the data, such as linear relationships, neighborhood averaging, and non-linear relationships.

## Models Used

- **Linear Regression**: A statistical method used to describe the relationship between a dependent variable and one or more independent variables.
- **k-Nearest Neighbors (kNN)**: A non-parametric method that predicts outcomes based on the average of the nearest neighbors in the dataset.
- **Random Forest**: An ensemble learning method that builds multiple decision trees and merges them to get a more accurate and stable prediction.

## Data

The dataset includes annual average concentrations of fine particulate matter (PM2.5) across the US Environmental Protection Agency’s monitoring network. Predictor variables include:
- CMAQ
- AOD (Aerosol Optical Depth)
- Population density (county and ZCTA level)
- Distance to primary and secondary roads
- Emission data from 2008 (PM2.5 and PM10)

### Data Source
- The data was obtained from the [EPA's monitoring network](https://github.com/rdpeng/stat322E_public/raw/main/data/pm25_data.csv.gz).

## Exploratory Data Analysis

Key insights from the exploratory data analysis include:
- **Heteroscedasticity**: Observed in predictors such as `imp_a10000`, `log_dist_to_prisec`, and `popdens_county`, which might affect the performance of linear regression.
- **Redundancy**: Predictors like `log_nei_2008_pm25_sum_10000` and `log_nei_2008_pm10_sum_10000` showed similar patterns, indicating potential redundancy.

## Model Performance

The models were evaluated using RMSE (Root Mean Square Error):
- **Linear Regression**: RMSE = 2.63
- **k-Nearest Neighbors**: RMSE = 2.39
- **Random Forest**: RMSE = 2.20

The Random Forest model performed the best, with the lowest RMSE, indicating its ability to handle complex, non-linear relationships in the data.

## Training and Testing

The dataset was split into training (75%) and testing (25%) subsets to assess model performance. Each model was trained using the training data and evaluated on the testing data.

## Final Model Assessment

The final assessment of the Random Forest model showed an RMSE of 2.20, suggesting that this model can accurately predict PM2.5 concentrations across the US. However, performance varied across different regions, particularly with poorer performance in less populated areas.

## Reflection

Through this project, I learned the importance of data pre-processing, model tuning, and understanding the assumptions underlying each model. Random Forest, in particular, proved to be an effective model, aligning with its reputation in handling complex datasets.

## Setup and Usage

### Requirements

To run the analysis, you will need the following R packages:
- `tidyverse`
- `rsample`
- `tidymodels`
- `randomForest`

### How to Run the Code

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/isobelbodefeld/predicting-air-pollution.git

2. Navigate to the Project Directory:
   cd predicting-air-pollution
   
3. Run the R Markdown File:
   Open project_analysis.Rmd in RStudio and click Knit to generate the report.
   
### Files in the Repository
- **project_analysis.Rmd**: The R Markdown file containing the analysis.
- **data.csv**: The dataset used for the analysis.
- **README.md**: This file, providing an overview of the project.

###Acknowledgments
I would like to thank:

- **Soumyabrata Bose**: For the guidance and support throughout the project.
- **Professor Steven Rashin**: For providing the context and structure for this assignment.