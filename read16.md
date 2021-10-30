# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)
## Machine Learning
Machine learning is a comprehensive approach to solving problems
### Key Terminology
+ Model - a set of patterns learned from data.
+ Algorithm - a specific ML process used to train a model.
+ Training data - the dataset from which the algorithm learns the model.
+ Test data - a new dataset for reliably evaluating model performance.
+ Features - Variables (columns) in the dataset used to train the model.
+ Target variable - A specific variable you're trying to predict.
+ Observations - Data points (rows) in the dataset.
### Machine Learning Tasks
| Supervised Learning | Unsupervised Learning |
| ---------------    | ----------------- |
| Supervised learning includes tasks for "labeled" data (i.e. you have a target variable).|	Unsupervised learning includes tasks for "unlabeled" data (i.e. you do not have a target variable). |
| In practice, it's often used as an advanced form of predictive modeling. | In practice, it's often used either as a form of automated data analysis or automated signal extraction. |
| Each observation must be labeled with a "correct answer."|Unlabeled data has no predetermined "correct answer."|
| Only then can you build a predictive model because you must tell the algorithm what's "correct" while training it (hence, "supervising" it).	 |	You'll allow the algorithm to directly learn patterns from the data (without "supervision").  |
|Regression is the task for modeling continuous target variables.
Classification is the task for modeling categorical (a.k.a. "class") target variables. | Clustering is the most common unsupervised learning task, and it's for finding groups within your data.|
##  Data Science 
This data science primer will cover exploratory analysis, data cleaning, feature engineering, algorithm selection, and model training. As you can see, those chunks make up 80% of the pie.

### 1- Exploratory Analysis
+ “Exploratory Analysis.” (Which is just fancy-talk for “getting to know” your data.)
+ Exploratory analysis is like sending scouts to learn where to deploy your forces!
+ Proper exploratory analysis is about answering questions. It's about extracting enough insights from your dataset to course correct before you get lost in the weeds.
+ However, exploratory analysis for machine learning should be quick, efficient, and decisive.
### 2- Data Cleaning
Proper data cleaning is the “secret” sauce behind machine learning… Well, it’s not really a “secret”… It’s just a bit boring, so no one really talks about it. But the truth is:

Better data beats fancier algorithms…
#### Remove Unwanted observations
The first step to data cleaning is removing unwanted observations from your dataset.

This includes duplicate or irrelevant observations.
| Duplicate observations | Unsupervised Learning |
| ------------------    | ------------------- |
| Duplicate observations most frequently arise during data collection|	Irrelevant observations are those that don’t actually fit the specific problem that you’re trying to solve. |
|1-  Combine datasets from multiple places| For example, if you were building a model for Single-Family homes only, you wouldn't want observations for Apartments in there. |
2- Scrape data | This is also a great time to review your charts from Exploratory Analysis. You can look at the distribution charts for categorical features to see if there are any classes that shouldn’t be there.|
3- Receive data from clients/other departments|Checking for irrelevant observations before engineering features can save you many headaches down the road. |
### 3- Feature Engineering


Feature engineering is about creating new input features from your existing ones.
In general, you can think of data cleaning as a process of subtraction and feature engineering as a process of addition.

### 4- Algorithm Selection
Why Linear Regression is Flawed

Simple linear regression models fit a "straight line" (technically a hyperplane depending on the number of features, but it's the same idea). In practice, they rarely perform well. We actually recommend skipping them for most machine learning problems.
+ In this regard, simple linear regression suffers from two major flaws:

+ It's prone to overfit with many input features.
It cannot easily express non-linear relationships.
#### Regularization in Machine Learning
Regularization is a technique used to prevent overfitting by artificially penalizing model coefficients.

+ It can discourage large coefficients (by dampening them).
+ It can also remove features entirely (by setting their coefficients to 0).
+ The "strength" of the penalty is tunable. (More on this tomorrow...)
### 5- Model Training
It might seem like it took a while to get here, but data scientists actually do spend most their time on the earlier steps:

+ Exploring the data.
+ Cleaning the data.
+ Engineering new features.

In  Model Training. We will swap algorithms in and out and automatically find the best parameters for each one.