# Property Loss Prediction Due to Fire Incidents
## Data Breif
* The dataset has 40 columns in total. After removing columns with more than 80% missing values and duplicate columns, we were left with 12 columns.
## Data Dictionary
  ![image](https://user-images.githubusercontent.com/48169929/226157068-86db3f3e-37ec-4eda-8d68-042c7c1f1040.png)
## Insights
### Number of incidents occured by hour
  * It can be seen that between 3 pm and 5 pm , most number of incidents have occured.
 ![image](https://user-images.githubusercontent.com/48169929/226158489-fadcf8bd-8854-47f5-b98f-40e06c34f2ab.png)
### Average Time (Minutes) taken to arrive after the alarm rings
* Here, fire fighters will arrive faster in MA , which is approx 5.24 minutes in average and WV fire fighters take longest time, which is 11.43 minutes.
![image](https://user-images.githubusercontent.com/48169929/226158565-e6982b0b-a8d5-4719-a6a2-490005767d6b.png)

## Multicollinearity Check
* Here, we can see that there is no multicollinearity exists between any two variables and all of them are indepedent
  ![image](https://user-images.githubusercontent.com/48169929/226157127-22f54f77-d0a3-42e0-9391-638dc5f057f3.png)

## Model Summary
* The predictor variables used for modeling have values in different ranges / scales , & hence the models' predictions were skewed initially since the predictor variables having values with a larger scale had a stronger influence on the model.We then standardized the variables to fix this problem.

* The predictor variables (numeric variables) used for modeling did not follow a Normal Distribution and this affected the model's performance. Transforming the distribution of the variables using Power Transformer helped to improve the R2 values for the models significantly.

* From the Summary Table for OLS model, we see that there are predictor variables having p-values greater than 0.05. Instead of dropping these variables, we have used these variables for modeling which has impacted the model's performance.

* We can see from the correlation heat map that none of the predictor variables have a strong correlation with the target variable 'PROP_LOSS' . Hence, we haven't been able to capture too much variance using the 11 Predictor Variables used in the subset. That is why the R2 values for all 3 models are found to be less than 0.3 for Test Set.Hence, more variables will have to incorporated into the model to capture more variance & improve the R2 values.

* The R2 values for test set is comparable to R2 values for the training set for all 3 models. Hence , we can say that these models are not overfitting. So, although the predictive power for the models is not great, we can still categorize these models as 'good'.

* To improve the prediction power , we have tried the Random Forest Model as well.We got the highest R2 value for the Random Forest Model , with an R2 value of 0.55 for the Training Partition & 0.52 for the Test Partition.The Mean Absolute Error & Median Absolute Error were also found to be the lowest for the Random Forest Model.


