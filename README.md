# Variable-Selection-Project

###  The task was to develop a model that would identify customers who will respond to a direct-mail marketing promotion and maximize profits. The data was of clothing from 
clothing store chain in New England with 2847 records and 119 variables. The issue was not only that the data has 119 variables with many categorical ones , the variables seems
divided into two groups i.e., original and derived one(description of derived variables was not available). Therefore multicollinearity was a big issue too. To handle this, the
option of variable selection came to rescue. As after initial cleaning steps, the data was divided into training and test. As objective was to identify customers who respond to
direct mail marketing, LogisticRegaression with variable selection seems best choice. For variable selection, I compared LASSO, Ridge, ElasticNet. In this Elastic Net performed 
the best, as it reduced 80 variables to 0, has lowest MSE and highest accuracy. Variables "ln lifetime average time between visits" variable in all the analysis found inversely
related with RESP which suggests that when the lifetime average is smaller the chance of Responding is high. However in the elastic net, "DAYS",responserate, 
"bc purchase visits", "sqrt blouses" are found directly related with RESP.

### Second task was to come up with a model to maximize profit. The absence of the labels of the variable names leaves many variable not clearly defined. However, log of total
spending provided in the dataset was my choice for target variable which as per my understanding reflects the profit and also log transformed. GridSearchCV is used to identify
the hyperparameters for l1 and l2 penality for XGBoost regression models. Both the models(with penality l1 and l2) are comparable. For first with l1 penality model, R-squared
and adjusted r-squared of training set is 0.95 whereas in test set the r-square is 0.84. Mean absolute error of this model is 22. Second with l2 penality model, R-squared and
adjusted r-squared of training set is 0.98 whereas in test set the r-square is 0.98. Mean absolute error of this model is 25.6. The most correlated variables to maximize the 
profit are COUPONS, TMONSPEND, STYLES, PSSPEND, MON from first model, whereas CCSPEND, CLASSES, MON in the second model.
