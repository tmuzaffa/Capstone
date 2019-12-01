# Capstone
Starbukcs Promotional strategy: A Machine Learning Approach


### Table of Contents

1. [Libraries used for the project](#libraries)
2. [Objective](#motivation)
3. [Problem Statement](#Problem)
3. [File Descriptions](#files)
4. [Analysis](#Analysis)
5. [Charts](#Charts)
6. [Acknowledgements](#acknowledgements)

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


## File Descriptions <a name="files"></a>




data:
- The data for this project was provided by Starbucks Inc. Starbucks data set consisted of three files namely
- portfolio.json
  -	profile.json
  -	transcript.json
portfolio.json contained metadata about each offer, profile.json contained demographic data of users, and transcript.json contained transactional data. 
portfolio.json:
portfolio.json consisted of below features
  -	channels (methods used to send offer to users)
  -	difficulty (minimum spending before offer applies)
  -	duration (duration validity of offer)
  -	id  (offer id)
  -	offer_type  (type of offer sent  to users)
  -	reward ( reward to be applied during valid offer duration after difficulty level achieved)
profile.json:
profile.json consisted of below features
  -	age (age of user)
  -	became_member_on (user became member on that day)
  -	gender (gender of user)
  -	id ( user id)
  -	income (income of user)

transcript.json:
profile.json consisted of below features
  -	event ( kind of event occurred, e.g. offer received, offer viewed, transaction made etc.)
  -	person (user id)
  -	time (time at which event occurred)
  -	value ( monetary value of the transaction)




Recommendation Engine:
- Recommendations_with_IBM.py
- Recommendations_with_IBM.ipynb


app:
- Recommendations_with_IBM.html.html





## Analysis<a name="Analysis"></a>

- By looking at the results of .describe(), we can see that the article_ids of both data frames  do not match with each other, df data frame has article id range from 0 to 1444, where as  df_content range from 0 to 1444.
- The number of unique articles that have at least one interaction are 714
- The number of unique articles on the IBM platform are 1051
- The number of unique users are 5148
- The number of user-article interactions are 45993
- Since we have no information about the new user, so collaborative filtering will not be the best option, as we will not be able to compare and match with other users and provide recommendations, however we can use top rated recommendations, and just recommend top rated articles to new users, which might not be the best option as well, as new user might have already read those artilces. I think to deal with such a problem, we should use FunkSVD

- As we have seen above that classes are highly imabalnced as there are lots of articles that user have no interacted with, as shown by the large proportion of class 0 as comapred to class 1. There might be some overfitting, as we have used 740 latent features, which makes the model complex and takes into account even small changes, however we can rectify that by making the model simpler and using less latent features. We can see above that the best accuracy of test, train sets can be achieved when we use approximately 100 latent features. If we use above, it leads to over fitting.

Since we can only predict for 20 users, so above fitting might not be accurate representaiton for our prediction. A better metric will be the article recommendation and not article interaction. It could be that user never interacted with the article becuase they donot like the it, or may be user likes the articles but have no just interacted with it yet on the platform.

We can also use A/B testing to see how our predictions are working. We can assign half users to control group and half to experimental group.



## Charts<a name = "Charts"></a>
![Histogram of user ineraction with articles](https://github.com/tmuzaffa/IBM-recommendation-engine-IBM-Watson/blob/master/01.png)
![Accuracy vs. number of latent features](https://github.com/tmuzaffa/IBM-recommendation-engine-IBM-Watson/blob/master/02.png)
![Accuracy vs number of latent features](https://github.com/tmuzaffa/IBM-recommendation-engine-IBM-Watson/blob/master/03.png)

  
  
## Acknowledgements<a name="acknowledgements"></a>

- This data set is  provided to us by IBM
- .dsecribe() > https://www.geeksforgeeks.org/python-pandas-dataframe-describe-method/
- Pyplot> https://matplotlib.org/3.1.1/gallery/pyplots/pyplot_text.html#sphx-glr-gallery-pyplots-pyplot-text-py

- Remove/find duplicates > https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.duplicated.html

- Nunique() > https://www.geeksforgeeks.org/python-pandas-dataframe-nunique/
- Most frequent index > ### Ref: https://stackoverflow.com/questions/48590268/pandas-get-the-most-frequent-values-of-a-column/48590361
- Unstack data frame > #Ref: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.unstack.html
- Setdiff1d  > https://docs.scipy.org/doc/numpy/reference/generated/numpy.setdiff1d.html
- Linear Algebra > Ref: https://docs.scipy.org/doc/numpy/reference/routines.linalg.html
