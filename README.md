# SC1015 Mini Project - Detection of Cardiovascular Diseases #

This is a SC1015(Introduction to Data Science and Artificial Intelligence) Mini Project which used the [Cardiovascular Disease Dataset](https://www.kaggle.com/sulianova/cardiovascular-disease-dataset) from Kaggle.

# Problem Definition 
#### Can we detect the presence of cardiovasular disease in a patient based on their current conditions?

# Contributors
- Lee Kar Jun Lester (@Lester0142) - Random Forest, MLP, K-Nearest Neighbours, Ensemble
- Lew Jian Ben Timothy (@timothy-lew) - Data Cleaning & Data Visualisation, Logistic Regression
- Endy Wong Yan Chang (@C210109) - Random Forest, MLP
 
# Models used
- [Logistic Regression](https://github.com/timothy-lew/dsai_mini_project/blob/main/Logistics_Regression.ipynb)
- [Random Forest](https://github.com/timothy-lew/dsai_mini_project/blob/main/Random_Forest.ipynb)
- [K-Nearest_Neighbors](https://github.com/timothy-lew/dsai_mini_project/blob/main/K-Nearest_Neighbors.ipynb)
- [Multi-layer Perceptron](https://github.com/timothy-lew/dsai_mini_project/blob/main/Multi-layer_Perceptron.ipynb)
- [Ensemble model](https://github.com/timothy-lew/dsai_mini_project/blob/main/Final_Ensemble.ipynb)

# Files
### **Data_Cleaning.ipynb** <br /> 
As mentioned above, the dataset we used is found from [Kaggle](https://www.kaggle.com/sulianova/cardiovascular-disease-dataset) and the formatted raw file is stored as [cardio.csv.](https://github.com/timothy-lew/dsai_mini_project/blob/main/Dataset/cardio.csv) From the dataset downloaded, we inspected the number of rows and columns, the type of data in each column and the correlation between each column. Next, we detected and removed outliers using boxplots. We then detected and removed multi-variate outliers using pairplot, resulting in a clean dataset with a much more even distribution than before. The clean dataset is then stored as [cardio_clean.csv.](https://github.com/timothy-lew/dsai_mini_project/blob/main/Dataset/cardio_clean.csv).

### Data_Visualization&EDA.ipynb <br /> 

In this notebook, we compared the dataset before and after cleaning using boxplots, histplots, violinplots, catplots and heat maps to show how the distribution of the dataset has changed through our cleaning. At the end, we then looked at the distribution and correlation of categorical variables after converting them to numberic variables.

### Final_Ensemble.ipynb <br /> 
In this notebook, we used the four other models to together for our prediction through ensemble modeling. A summary of the effectiveness of each model is also presented at the end.  

### K-Nearest_Neighbors.ipynb <br /> 
In this notebook, we tuned the hyperparameters for each parameter of KNeighborsClassifiers separatedly, resulting in a small increase in test accuracy. 

### Logistics_Regression.ipynb <br /> 
In this notebook, numeric columns in our dataset was used to predict presence of cardiovascular disease through logistic regression. The logistic regression graph for each variable was plotted to show the relationship between cardiovascular disease and each variable individually.

### Multi-layer_Perceptron.ipynb <br /> 
In this notebook, GridSearchCV was first used for hyperparameter tuning based on a set of input variables to find the optimal parameters for MLPClassifier. Due to getting a low accuracy on the train test, we suspected that the MLP model was underfitted. We then plotted graphs to show the relationship between each hyperparameter and accuracy as well as find out the optimal value for each parameter. In the end, we concluded that our inital variables were quite well fitted and we were unable to increase the accuracy any further after using the optimal values for each individual hyperparameter.

### Random_Forest.ipynb <br /> 
In this notebook, we improved our initial random forest model by using the Area Under Curve(AUC) score for each hyperparameter. The graph for Train AUC and Validation AUC against each variable was plotted to provide visualisation for optimal values for each hyperparameter. The optimal values were then used in our model to obtain the highest possible accuracy usng RandomForestClassifer.

# Conclusion

Out of our five models, we recommend using the ensemble model as the accuracy score from cross_val_score of the highest among all the models used. In our original problem statement, we seek to use Machine learning to help in the diagnosis of Cardiovascular diseases. However, we realize that the low correlation of any particular predictor results in a lower than preferred yield/ accuracy. Diseases are usually inter-related to one another, such that multiple diseases could all result in the same symptoms. Furthermore, factors such as obesity might result in a higher chances of contracting illnesses as we always learn that correlation does not imply causation. A [study](https://pubmed.ncbi.nlm.nih.gov/34048921/) recorded in the journal of Cardiac Failure showed that, the rates of HF misdiagnosis ranged from 16.1% in hospital setting to 68.5% when general practitioner referred patients to specialist setting. Hence, we should not let our low accuracy shut down the possibilities of machine learning in the medical field. Perhaps, inputting more specific data can increase the accuracy of our machine learning model to give a better diagnosis prediction. Furthermore, one of the use cases we envisioned at the start of the mini project was to create a Machine learning model that can predict cardiovascular disease not to be conclusive or exhaustive, but to raise awareness of heart disease to the general public who are usually ignorant about such diseases. This model can be used to prompt users to visit a clinic or specialist for further check up if they are flagged as of moderate or high risk beyond the usual regular check ups.


