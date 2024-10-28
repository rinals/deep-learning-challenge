# Alphabet Soup Deep Learning Model Report

## Overview of the Analysis

The purpose of this analysis is to develop a deep learning model that can predict the success of funding applicants based on various features. Alphabet Soup, a nonprofit foundation, wants to maximize its funding efficiency by identifying applicants with the highest likelihood of success. Using a neural network model, this project classifies whether applicants will use funding successfully.

## Results

### Data Preprocessing

- **Target Variable**: 
  - The target variable is `IS_SUCCESSFUL`, which indicates whether an applicant’s funding was used successfully.

- **Feature Variables**:
  - Features include the following variables:
    - `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, `ASK_AMT`
  - These variables provide important information about each application and help the model predict success.

- **Removed Variables**:
  - The following variables were removed because they are neither targets nor features:
    - `EIN` (Employer Identification Number) and `NAME`
  - These columns were dropped as they do not contribute meaningful information for prediction.

### Compiling, Training, and Evaluating the Model

- **Neurons, Layers, and Activation Functions**:
  - **Layers and Neurons**: The neural network model has three hidden layers:
    - The first layer has 100 neurons, the second layer has 50 neurons, and the third layer has 25 neurons.
  - **Activation Functions**: ReLU was used for the hidden layers, and sigmoid for the output layer.
  - This structure was selected to balance complexity and performance, aiming to capture patterns within the dataset without overfitting.

- **Model Performance**:
  - The initial model achieved an accuracy close to the target, with the best model showing approximately 73% accuracy.
  - While it did not meet the 75% target, the model demonstrated reasonable predictive power given the dataset’s complexity.

- **Optimization Steps**:
  - Three main optimization attempts were made to improve model performance:
    1. **Increased Neurons and Added Layers**: More neurons were added to existing layers, and a third layer was introduced to capture more complex patterns.
    2. **Changed Activation Functions**: The activation function was changed to `tanh` for hidden layers in one attempt to see if this improved learning.
    3. **Dropped Noisy Variables**: The `ASK_AMT` variable was dropped to test if removing potentially noisy data could improve the model’s accuracy.

### Summary

The deep learning model for Alphabet Soup’s funding prediction task achieved reasonable results, with a peak accuracy of about 73%. While this falls slightly below the target of 75%, the model effectively identified key patterns in the data. 

**Recommendation**:
For further improvement, a different model, such as a **Random Forest Classifier** or **Gradient Boosting Model**, could be considered. These models excel at handling structured/tabular data and may outperform neural networks in terms of accuracy and interpretability for this classification problem.
