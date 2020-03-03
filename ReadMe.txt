Amazon Rating based Recommender system. Here are the step by step workflow:

1> Load data
2> perform EDA
	a> Check for sparsity
	b> Check for null values
	c> Check rating attribute mean,std,count, quartile and distribution.
	d> Check Users trend on rating
	e> Check rating trend of products
3> Take subset of dataset. decision factor : To take only users who has given 50 or more ratings.
4> Check the EDA of the new dataset.
5> Split the data randomly into train and test dataset using 70:30 ratio.
6> Build Popularity Based Models. Following 4 popularity based model are developed:
	a> Highest Mean rating based
	b> Highest count of rating based
	c> Weighted Average rating based.
	d> Damp rating based.
7> Review and compare all the above popularity based models.
Collaborative Filtering model
8> Develop Model Using SVD - Matrix Factorization
9> Build Models Using Surprise Package:
Important Note: Due to Computation limitation and Memory limitation. We have to further reduce the dataset.
Option 1: First 50000 records.
Option 2: Take data of products which has atleast 5 ratings. 

Option 1 was of no useful.again Memory error was reported.
Option 2 was executing successfully. Hence further model building shall be using option 2 dataset.

10> Build item-item based KNN model
11> Build user-user based KNN model
12> Review the Accuracy metrics of the 2 models.
13> Check the best and worst predictions of the 2 models
14> Compare both the models.

15> Suprise package has multiple algorithms. Let's build model using all the below algorithms:
The prediction_algorithms package includes the following prediction algorithms:

	a> random_pred.NormalPredictor    Algorithm predicting a random rating based on the distribution of the training set, which is assumed to be normal.
	b> baseline_only.BaselineOnly    Algorithm predicting the baseline estimate for given user and item.
	c> knns.KNNBasic    A basic collaborative filtering algorithm.
	d> knns.KNNWithMeans    A basic collaborative filtering algorithm, taking into account the mean ratings of each user.
	e> knns.KNNWithZScore    A basic collaborative filtering algorithm, taking into account
	f> knns.KNNBaseline    A basic collaborative filtering algorithm taking into account a baseline rating.
	g> matrix_factorization.SVD    The famous SVD algorithm, as popularized by Simon Funk during the Netflix Prize.When baselines are not used, this is equivalent to Probabilistic Matrix Factorization. 
	h> matrix_factorization.SVDpp    The SVD++ algorithm, an extension of SVD taking into account implicit ratings.
	i> matrix_factorization.NMF    A collaborative filtering algorithm based on Non-negative Matrix Factorization.
	j> slope_one.SlopeOne    A simple yet accurate collaborative filtering algorithm.
	k> co_clustering.CoClustering    A collaborative filtering algorithm based on co-clustering.

16> Choose the top 2 algorithm model by using RMSE Accuracy metrics
17> Fine tune hyper-parameter of them
10> Build models using the fine tuned estimators.
11> Review the Accuracy metrics of the 2 models.
13> Check the best and worst predictions of the 2 models
14> Compare both the models.
15> Get top=k recommendations by both models.
16> Compute classification Accuracy metrics of both models.
	a> Precision or true positive accuracy (Confidence)
	b>Recall or true positive rate (sensitivity)
	c> Fallout or false positive rate
	d>Miss rate or false negative rate
	e> Inverse precision or true negative accuracy
	f>Inverse recall or true negative rate (also called specificity)
	g>The F1-measure
	h>Markedness
	i>Informedness
	j> The Matthews Correlation
	K>AP@k
	l>MAP@k
