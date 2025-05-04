# Predicting Temperature Changes Over Time to Indicate Climate Trends

## Group Members and Course
- Luke Carignan (STAT-427)
- Gracie Abrahams (STAT-427)
- Jeffrey Mann (STAT-427)

## Topic
This project aims to analyze historical climate data to examine changes in temperature and weather patterns over the years. Specifically, we will investigate how temperature trends have evolved and develop predictive models to forecast future temperature changes. Additionally, we will explore related climate factors such as precipitation, wind speed, and extreme weather classifications.  
Our dataset comes from the Climate Change Service (CS3), specifically the ERA5 hourly time series data on single levels from 1940 to present, with a focus on Washington, D.C. This dataset contains approximately 75,000 observations recorded hourly and includes 17 variables relevant to weather and climate conditions.

### Questions of Interest
#### Regression Analysis:
- Predicting future temperature patterns based on past weather data. **
- Estimating precipitation (tp) using temperature, pressure, and wind speed.
- Modeling wind speed (u10, v10) from other weather variables.

#### Classification Analysis:
- Classifying extreme weather events (e.g., heavy rain, high winds, extreme heat). **
- Determining whether an hour is classified as rainy vs. dry based on weather conditions.

Starred questions were the final questions we modeled.

## Planned Approach
### Literature Review:
Identify at least one article or publication per group member relevant to the topic. It does not have to be a scholarly article but it shall provide context for the topic and questions of interest to help in framing the analysis.

1. The article discusses how climate change impacts energy consumption, particularly in relation to heating and cooling. As temperatures rise, heating demand generally decreases, but air conditioning needs increase, especially in tropical regions. This shift can lead to more fragmented electricity consumption, challenging grid management. Societal choices, such as air conditioning adoption, further influence energy demand, with variability in efficiency between different types of air conditioners.  
   [Read Article](https://www.polytechnique-insights.com/en/columns/planet/how-climate-change-will-affect-our-energy-consumption/#:~:text=And%20yet%20our%20heating%20needs,the%20electricity%20system%20to%20manage.)

2. The article discusses the environmental impacts of energy production and consumption. The majority of U.S. electricity generation relies on fossil fuels, releasing harmful gases like CO2, sulfur dioxide, and nitrogen oxides, which contribute to global warming, acid rain, and other environmental issues. Increased consumption intensifies emissions. The article suggests adopting green energy providers and reducing personal energy consumption to mitigate these effects.  
   [Read Article](https://justenergy.com/blog/impact-of-energy-production-consumption-environment/)

3. This article examines how climate classification affects building energy use and environmental impact. It finds that buildings in the same climate zone but with different humidity conditions can have up to 47% higher energy consumption, despite similar heating and cooling degree days. The study highlights that degree days alone are inadequate for predicting energy use and suggests incorporating humidity into energy policies. Additionally, emissions (CO2 and SO2) can vary significantly within a climate zone, emphasizing the need for geographic prioritization in carbon-neutral policies.  
   [Read Article](https://www.sciencedirect.com/science/article/abs/pii/S0360544223018418)

### Data Assessment:
#### Identification of the Data Set and Its Source:
- **Climate Change Service (CS3)** provides historic climate data.
- **ERA5 Hourly Time Series (1940-2025)**.
- **Location Focus**: Washington DC.

This dataset is provided by the Climate Change Service (CS3), which supports society by providing authoritative information about the past, present, and future climate in Europe and the rest of the world. The dataset focuses on hourly time series data for Washington, D.C. from 1940 to the present.

#### Dataset Overview:
- 75,000 rows of data (hourly).
- 17 variables related to weather and climate conditions.
  
##### Variable Descriptions:
- **u10**: Wind speed in the east-west direction (negative values → west, positive values → east).
- **v10**: Wind speed in the north-south direction (negative values → south, positive values → north).
- **t2m**: Air temperature at 2 meters above the ground (in Kelvin).
- **d2m**: Dew point temperature at 2 meters above the ground (in Kelvin).
- **t2m_farenheit**: Air temperature converted to Fahrenheit.
- **d2m_farenheight**: Dew point temperature converted to Fahrenheit.
- **msl**: Mean sea level pressure (Pascals).
- **sp**: Surface air pressure (Pascals).
- **tp**: Total precipitation (rain, snow, etc.) in meters.
- **sst**: Sea surface temperature.
- **lat/long**: Location coordinates.
- **year**: Year from 1940-2025.
- **month**: Month (1-12).
- **day**: Day of the month (1-31).
- **hour**: Hour of the day (1-24).
- **valid_time**: Time stamp (hourly).

### Planned Methods:
We plan to use linear and/or polynomial regression, depending on the best fit, to make our predictions for regression questions. If there are nonlinear temperature patterns, we can assess polynomial regression patterns and adjust our models. For classification, we will explore logistic regression models to classify extreme weather events and other factors, using accuracy, precision, recall, F1, and ROC curves for evaluation.

#### Multicollinearity and Model Comparison:
To check for multicollinearity, we will calculate the VIFs for each predictor in the regression models, especially focusing on temperature-related variables. We will consider removing or combining predictors if the VIF exceeds 5-10. For model comparison, we will evaluate performance using MSE, R², and cross-validation for regression models, and accuracy, precision, recall, and ROC scores for classification models.

### Ethical Concerns:
It is crucial to understand the impact of climate data models, especially when using predictions to inform energy consumption and policies. We must ensure that climate predictions are not overgeneralized and that they are used responsibly to avoid creating false alarms or ineffective policies.

### Risk Assessment and Mitigation:
We aim to be transparent about any data quality issues and address potential biases by using cross-validation, regularization, and other techniques. We will ensure that our predictions are not used for generalized claims, particularly when predicting climate trends.

## Deliverable:
The final deliverable will be a **poster presentation** summarizing our findings, methodologies, and key takeaways. This will include:
- A description of the dataset and methods used.
- Key findings and insights into climate trends and their potential implications.

## Schedule and Hours:
| Week | To Do/Time Required                                  | Goal/Expected Outcome                               |
|------|------------------------------------------------------|-----------------------------------------------------|
| Week 10 | Finalize research question, find dataset, find relevant scholarly work, and do exploratory data analysis | Finish proposal and have data ready to work with    |
| Week 11 | Clean dataset, create new variables, continue EDA, and begin preliminary modeling | Clean data ready for modeling and EDA completed    |
| Week 12 | Classification and regression modeling, evaluation metrics | Regression and classification models created, ready for evaluation |
| Week 13 | Cross-validation, checking for bias, model comparison | Data validated, reports on bias, model comparisons completed |
| Week 14 | Final review, model touch-ups, poster creation | Completed code, poster, and presentation practice |

## Group Member Responsibilities:
We used this Github Repo as a shared place to commit all of our changes throughout the project. We initially worked on a Colab notebook, and then migrated our changes here for more efficiency
Gracie - Exploratory Analysis + Classification (KNN, LDA/QDA, Logistic Reg & Evaluation)
Jeffrey - Regression (Linear Reg, Polynomial, Ridge/LASSO) + Evaluation/CV

Each member attended group meetings and contributed to data cleaning, exploratory research, and model development. We then put together our poster with our findings.

## Summary:
This project aims to analyze and predict temperature trends over time using historical climate data from Washington, D.C. By leveraging regression and classification models, we will examine climate change indicators and their potential implications for energy consumption and environmental policies. The final deliverable will be a poster presentation summarizing our findings, methodologies, and key takeaways.

##Directory:
- analysis: Contains our analysis in R
   -   climate-classification.qmd : main R file with evaluation, models, evaluation
   -   climate.html : rendered html file
     
- data: Contains our dataset
  - Climate-Data.csv : updated dataset from 2000-2025 with DC coordinates
  - ClimateData.csv : original dataset from 1940-2025 with swapped lat and long coords (set in Antarctica)
  - README.md : You are here!
  - STAT427-Poster.pptx.pdf : Poster with findings
  - STAT427_FinalProject-Recording : Video Recording Presenting our Poster

## Resources:
- [CDS Datasets](https://cds.climate.copernicus.eu/datasets)
- [Dataset Overview](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-single-levels-timeseries?tab=overview)
- [Dataset Documentation](https://confluence.ecmwf.int/pages/viewpage.action?pageId=505390919)
- [Article Related to Dataset](https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.3803)
