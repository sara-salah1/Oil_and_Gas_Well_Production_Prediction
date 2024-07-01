# Oil_and_Gas_Well_Production_Prediction

The primary goal is twofold:

Capture Complex Relationships: Understand and analyze the intricate relationships between various features and the target variables in the dataset.
Build a Predictive Model: Develop a performant predictive model to comprehend feature interactions and their effects on the target variables, NormalizedOilEUR and NormalizedGasEUR.



# Dataset Description
The dataset comprises 9206 records with 15 attributes, encompassing a wide range of features related to well characteristics and production metrics. The attributes include:

**WellID**: A unique 10-digit identifier for each well.
**BVHH**: A measure of rock quality at the well's location.
**FormationAlias**: The geological zone or rock formation from which the well extracts oil and gas.
**NioGOR**: Gas-to-oil ratio in the Niobrara formation at the well's coordinates.
**CodGOR**: Gas-to-oil ratio in the Codell formation at the well's coordinates.
**LateralLength**: Length of the drilled well in feet.
**ProppantPerFoot**: Amount of proppant used per foot of the well's length.
**FluidPerFoot**: Amount of fluid used per foot of the well's length.
**{Left/Right}Distance**: Distance to the nearest neighboring well on the left/right.
**{Left/Right}NeighbourType**: Type of neighboring well (parent, co-developed, or none).
**TVD**: True Vertical Depth of the well.
**NormalizedOilEUR**: Normalized oil production in bbl/ft over the well's lifetime.
**NormalizedGasEUR**: Normalized gas production in mcf/ft over the well's lifetime.


# Libraries
A variety of libraries are utilized for data manipulation, visualization, modeling, and evaluation:

Data Manipulation: `numpy`, `pandas`
Data Visualization: `missingno`, `seaborn`, `matplotlib`, `plotly`
Machine Learning: `sklearn`, `xgboost`
Metrics: `r2_score`,`classification_report`


# Data Collection and Analysis

1. Load the Dataset: Import the dataset and display basic information.
2. Identify Missing Values: Use visualizations to identify and understand the patterns of missing values.


# Data Preprocessing
## Data Cleaning:

- Visualize the distribution of features and missing values.
- Use the KNN imputer to fill missing values for numerical and categorical columns.
- Handle negative values and outliers.
- Fill null values using appropriate methods (mean, median, or specific logic based on domain knowledge).
  
## Feature Engineering:

- Extract new features such as ProppantPerFootRatio, FluidPerFootRatio, ProppantFluidRatio, TotalDistance, AverageGOR, LogTVD, and IsNiobrara/IsCodell.
- Drop unwanted features.
- Handle outliers using the IQR method.

  
## Data Visualization:

- Visualize numerical features using histograms, box plots, and scatter plots.
- Visualize categorical features using bar plots.
- Explore correlations using heatmaps.

  
# Model Building
## Data Splitting:

- Split data into training and test sets.
- Separate features and targets for modeling.
  
## Model Training:

- Train various regression models including XGBRegressor, RandomForestRegressor, Lasso, Ridge, GradientBoostingRegressor, and SVR with RBF Kernel.
- Evaluate models using R² score on training and test sets.
  
## Pipeline and Grid Search:

- Implement pipelines for data preprocessing and modeling.
- Use GridSearchCV for hyperparameter tuning.
  
## Models Used
- XGBRegressor: Used for predicting oil and gas production with GridSearchCV for hyperparameter tuning.
- Random Forest Regressor: Used for predicting oil and gas production.
- Lasso: Used for predicting oil and gas production with hyperparameter tuning for regularization strength.
- Ridge: Used for predicting oil and gas production with hyperparameter tuning for regularization strength.
- Gradient Boosting Regressor: Used for predicting oil and gas production.
- SVR with RBF Kernel: Planned for future inclusion.
