# <p align="center">Project 4: Machine Learning
## Data Analytics project to build and utilize a machine learning model to predict student performance/academic outcomes
### Project Summary
This project developed a machine learning model to predict student performance based on available attributes such as grades, demographics, social/personal characteristics, and school information. We achieved an accuracy score of 89%, which we suspect could be increased with a larger set of data to train the model. But we also investigated decreasing the number of features and were able to achieve a comparable accuracy with only the top ten features as determined by specific scorers. This kind of model could provide actionable insights for teachers and school administrators, helping them to identify students at risk of subject failure or underperformance and allowing for targeted academic intervention.
### Data Source
A [dataset](https://archive.ics.uci.edu/dataset/320/student+performance) from two Portuguese schools via school reports and questionnaires, publicly available on the UC Irvine Machine Learning Repository.
### Ethical Considerations
This is a publicly-available dataset that contains no information for the identification of specific individuals, and is licensed under a [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/legalcode) license, allowing for the sharing and adaptation of the dataset for any purpose provided that credit is attributed to the source.
### Methodology
- Initial exploration of the data:
    - The data was downloaded and accompanying information regarding the features was reviewed to understand what they represented.
- ETL:
    - The data was in two different sets for two different subjects, one for math and the other for Portuguese.
    - A table for each was created in a SQL database hosted locally using pgAdmin 4.
    - CSV files were output from the SQL database using pgAdmin 4 for ease of reading into Pandas DataFrames.
- Preprocessing:
    - Converted the target G3 numerical scores (range 0 to 20) to Pass (greater than or equal to 10) or Fail (below 10)
    - Converted categorical variables to "dummy" variables
    - Scaled our dataset via "StandardScaler" to reduce the impact of extreme values/outliers
- Initial model:
    - Used default sklearn split of 75% training data, 25% testing
    - Started with 100 nodes in the first hidden layer
    - 80 nodes were used in the second hidden layer
    - Used "relu" activation function for both
    - Compiled the model using "adam" optimizer function
    - Ran 100 epochs to train the model
- Optimizing parameters to improve the model:
    - Added an additional hidden layer
    - Adjusted the number of nodes per layer, sticking to the "upside-down wedding cake" approach
    - Changing the activation function lowered the accuracy score
    - Trying the "MinMaxScaler" lowered the accuracy score
    - Trying to add stratify also lowered the accuracy score
- Inspection of the model/analysis of features' importance:
    - Two scoring functions of [Permutation Feature Importance](https://scikit-learn.org/stable/modules/permutation_importance.html) were used to evaluate the weight of features on the models:
        1. [r2_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.r2_score.html#sklearn.metrics.r2_score)
        2. [explained_variance_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.explained_variance_score.html#sklearn.metrics.explained_variance_score)
    - Keeping only the top ten most important features as determined by the above scorer(s) resulted in comparable accuracy scores
### Usage
Download the contents of this repository to one directory, and explore the files/scripts.
### License
[MIT License](https://opensource.org/licenses/MIT)
### Contact (Individual Contributors' GitHub Pages)
- [ktaytg](https://github.com/ktaytg)
- [cengelhart0120](https://github.com/cengelhart0120)
- [Alejandrogz1604](https://github.com/Alejandrogz1604)
- [chalisal](https://github.com/chalisal)
