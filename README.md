# Capstone
Starbukcs Promotional strategy: A Machine Learning Approach

$\alpha$
### Table of Contents

1. [Libraries used for the project](#libraries)
2. [Objective](#motivation)
3. [Problem Statement](#Problem)
4. [Metrics] (#metric)
4. [File Descriptions](#files)
5. [Analysis](#Analysis)
6. [Charts](#Charts)
7. [Acknowledgements](#acknowledgements)

## Libraries used for the project <a name="libraries"></a>

Following python libraries:

1. Pandas
2. Matplotlib 
3. NLTK
4. NumPy
5. Pickle
6. Seaborn
7. Sklearn
8. LabelEncoder
9. StandardScaler
10. Shuffle
11. GridSearchCV
12. StratifiedKFold
14. Confusion_ MAtrix
15. Log_Loss
16. F1 Score
17. PCA
18. Mean Squared Error
19. XGBoost


I used the Anconda python distribution with python 3.0

## Objective<a name="motivation"></a>

The objective of this project is to combine transaction, demographics, and offer data to determine which demographic group respond best to which offer type. 

This data set is  provided to us by Starbucks

## Problem Statement<a name="problem"></a>
The goal is to determine which demographics respond best to what type of offer so that they can be sent only that type of offer to maximize profitability.  We also want to make sure, not to send offers to customers who are already loyal to Starbucks brand as they will make purchases with or without offer, and to the customers who might stop purchasing because of offers as they might not want to participate in the company marketing campaign. The task involved in this project are the following:
1)	Pre-process portfolio.json, profile.json, and transcript.json
2)	Predict age, gender, and income distribution of missing data using gradient boosted tree regressor and classifier. 
3)	Merge predicted data for missing values with known data
4)	Do feature engineering to calculate monthly profits made for each offer type
5)	Analyze monthly profits for each offer type and look at trends
The final analysis are expected to shed light on the type of offer and demographics that Starbucks should target for maximum profitability.

## Metrics: <a name="metric"></a>
 Metric used to see the best offer is monthly profit and number of transactions in that particular month. 
Metrics used for data pre-processing are below
-	Root Mean Squared Error (RMSE) (Wikipedia, n.d.)
RMSE is a commonly used to optimize the models. Optimization of model involve minimizing 
- F1 score 

## File Descriptions <a name="files"></a>


 data:
- The data for this project was provided by Starbucks Inc. Starbucks data set consisted of three files namely
- portfolio.json
  -	profile.json
  -	transcript.json
portfolio.json contained metadata about each offer, profile.json contained demographic data of users, and transcript.json contained transactional data. 
- portfolio.json:
portfolio.json consisted of below features
  -	channels (methods used to send offer to users)
  -	difficulty (minimum spending before offer applies)
  -	duration (duration validity of offer)
  -	id  (offer id)
  -	offer_type  (type of offer sent  to users)
  -	reward ( reward to be applied during valid offer duration after difficulty level achieved)
- profile.json:
profile.json consisted of below features
  -	age (age of user)
  -	became_member_on (user became member on that day)
  -	gender (gender of user)
  -	id ( user id)
  -	income (income of user)

- transcript.json:
transcript.json consisted of below features
  -	event ( kind of event occurred, e.g. offer received, offer viewed, transaction made etc.)
  -	person (user id)
  -	time (time at which event occurred)
  -	value ( monetary value of the transaction)

month_data.csv:
- Month data csv can be found at this google drive link >> https://drive.google.com/open?id=1xBSCFzOz3u4_acn9XshoDW1qZzMCU0SB
- This was created after feature engineerig, and running data on the model

new_profile.csv:
- New profile was created after predicitng missing values

all_offer_profile2.csv:
- profile data catered to each profile

Starbucks_Capstone_notebook.ipynb:
- Contains the intro of the project provided by Udacity

Readme.md:
- Readme file

Date processing.ipynb:
- Contains explorary data analysis, use of gradient boosted tree to predict missing values

All Offers.ipynb:
- Contains analysis/visulaization of all offers

gen_mod_pickle.dat
- Saved model of gender
income_mod.pickle.dat
- Saved model of income
age_mod.pickle.dat
- Saved model of age

Starbukcs Promotional Strategy.pdf
- Report of the project


transcipt.csv
- Transactional data in csv format


## Analysis<a name="Analysis"></a>

- By using these model we were able to predict age, income, and gender of missing values in the data set. Below are the new age, gender, and  income distribution
Now we can see the income distribution of the users with missing data, it is uniform distribution however our RMSE metric is very high 26188 but since the model is only relying on engineered features, and model has not insight into the characteristic of the data so this results is acceptable. 
- Similarly we did the age prediction of the missing values. RMSE again was not favorable and was high 17.84 but as suggested above, model is relying on engineered features so the result is acceptable
- Similarly we predicted the gender for missing values with F1 score of 0.59



## Charts<a name = "Charts"></a>
![Age distribution after prediction](https://github.com/tmuzaffa/Capstone/blob/master/pic1.png)
![Gender distribution after prediction donut chart](https://github.com/tmuzaffa/Capstone/blob/master/pic2.png)
![Gender distribution after prediction](https://github.com/tmuzaffa/Capstone/blob/master/pic3.png)
![Income distribution afer prediction](https://github.com/tmuzaffa/Capstone/blob/master/pic4.png)

  
  
## Acknowledgements<a name="acknowledgements"></a>

- This data set is  provided to us by Starbucks
- .dsecribe() > https://www.geeksforgeeks.org/python-pandas-dataframe-describe-method/
- Pyplot> https://matplotlib.org/3.1.1/gallery/pyplots/pyplot_text.html#sphx-glr-gallery-pyplots-pyplot-text-py
- Remove/find duplicates > https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.duplicated.html
- Nunique() > https://www.geeksforgeeks.org/python-pandas-dataframe-nunique/
- Most frequent index > ### Ref: https://stackoverflow.com/questions/48590268/pandas-get-the-most-frequent-values-of-a-column/48590361
- Unstack data frame > #Ref: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.unstack.html
- Setdiff1d  > https://docs.scipy.org/doc/numpy/reference/generated/numpy.setdiff1d.html
- Linear Algebra > Ref: https://docs.scipy.org/doc/numpy/reference/routines.linalg.html
- PCA > Ref: https://www.dezyre.com/data-science-in-python-tutorial/principal-component-analysis-tutorial
- PCA2 > Ref: ftp://statgen.ncsu.edu/pub/thorne/molevoclass/AtchleyOct19.pdf
- GridSearchCV > Ref:: https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html
- Siau, K., & Yang, Y. (2017). Impact of Artificial Intelligence, Robotics, and Machine Learning on Sales and Marketing. Proceedings of the Twelfth Midwest Association for Information Systems Conference,, (p. 48). Springfield.
- Sundsoy, R., Bjelland, J., Asif, M. I., Pentalnd, A., & Yves-Alexandre, d. M. (n.d.). Big Data-Driven Marketing: How Machine Learning Outperforms Marketers’ Gut-Feeling. In Social Computing, Behavioral-Cultural Modeling and Prediction. Springer.
- Towardsdatascience. (n.d.). Retrieved from https://towardsdatascience.com/understanding-confusion-matrix-a9ad42dcfd62
- Mean Squared Error > Ref: https://en.wikipedia.org/wiki/Mean_squared_error
- F1 Score> Ref: https://en.wikipedia.org/wiki/F1_score
- Precision and Recall > Ref:https://en.wikipedia.org/wiki/Precision_and_recall
- XGBoost > Ref: https://xgboost.readthedocs.io/en/latest/python/python_api.html
- Starbuck logo > Ref: https://en.wikipedia.org/wiki/Starbucks
- Datetime > Ref: https://stackoverflow.com/questions/27506367/python-pandas-integer-yyyymmdd-to-datetime
- Date Extraction > Ref: https://stackoverflow.com/questions/21954197/which-is-the-fastest-way-to-extract-day-month-and-year-from-a-given-date
- Dictionary > Ref: https://stackoverflow.com/questions/46405974/extract-values-from-dictionaries-in-dataframe-columns
- Pipe Character > Ref: https://stackoverflow.com/questions/5988665/pipe-character-in-python
- Rename Dataframe > Ref: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.rename.html
- Rounding Number > Ref: https://www.knowledgehut.com/blog/programming/python-rounding-numbers
- https://github.com/scikit-learn/scikit-learn/issues/3123
- DataFrame > Ref: https://stackoverflow.com/questions/46405974/extract-values-from-dictionaries-in-dataframe-columns
- HotEncoder > Ref: https://firecharmca.wordpress.com/2018/03/22/feature-engineering-categorical-value-onehotencoder-and-why-not/
- LabelEncoder > Ref: https://stackoverflow.com/questions/53970350/valueerror-contains-new-labels-when-trying-to-label-encode-in-python


