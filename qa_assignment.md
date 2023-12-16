# Q/A Assignment
Q1. You train Logistic Regression with a certain set of features and learn weights $w_0$, $w_1$ till $w_n$.
Feature $n$ gets weight $w_n$ at the end of training. Say you now create a new dataset where you duplicate feature $n$ into feature $(n+1)$ and retrain a new model. Suppose this new model weights are $w_{new_0}$, $w_{new_1}$ till $w_{new_n}$, $w_{new_{n+1}}$. What is the likely relationship between $w_{new_0}$, $w_{new_1}$ , $w_{new_n}$,  and $w_{new_{n+1}}$?

Answer:
When you duplicate feature $n$ into feature $(n+1)$ and retrain a new model, the weights of the original feature $n$ and the duplicated feature $(n+1)$ might change due to the model's optimization process. However, the relationship between these weights is not straightforward and can vary depending on multiple factors such as the nature of the data, regularization techniques used, and the convergence of the optimization algorithm.

In general, the weights $w_{new_n}$ and $w_{new_{n+1}}$ for the duplicated features might not necessarily be the same as $w_n$ and could differ significantly. The exact relationship between $w_{new_0}$, $w_{new_1}$, $w_{new_n}$, and $w_{new_{n+1}}$ cannot be determined without analyzing the specific data and the model training process.

When duplicating a feature and retraining the model, the new weights are likely to be influenced by interactions with other features, potential multicollinearity issues between the duplicated features, and the way the model adapts during training.

Sources used:

1. Hastie, T., Tibshirani, R., & Friedman, J. (2009). The Elements of Statistical Learning: Data Mining, Inference, and Prediction. Springer Science & Business Media.
2. Bishop, C. M. (2006). Pattern Recognition and Machine Learning. Springer.

Q2. You currently have an email marketing template A and you want to replace it with a better template. A is the control_template. You also test email templates B, C, D, E. You send exactly 1000 emails of each template to different random users. You wish to figure out what email gets the highest click through rate. Template A gets 10% click through rate (CTR), B gets 7% CTR, C gets 8.5% CTR, D gets 12% CTR and E gets 14% CTR. You want to run your multivariate test till you get 95% confidence in a conclusion. Which of the following is true?

    1. We have too little data to conclude that A is better or worse than any other template with 95% confidence.
    2. E is better than A with over 95% confidence, B is worse than A with over 95% confidence. You need to run the test for longer to tell where C and D compare to A with 95% confidence.
    3. Both D and E are better than A with 95% confidence. Both B and C are worse than A with over 95% confidence

Answer:
To determine the best-performing email template with 95% confidence, we need to analyze the results based on statistical significance.

Given the click-through rates:

* Template A: 10%
* Template B: 7%
* Template C: 8.5%
* Template D: 12%
* Template E: 14%

It appears that Template E has the highest CTR at 14%. However, to ascertain the significance of these results and compare them against Template A, statistical testing is necessary.

Comparing Template A to the others:

Template E: With a 95% confidence level, Template E outperforms Template A as its CTR is significantly higher.

Template B: At a 95% confidence level, Template B's CTR is significantly lower than Template A's.

Template C: Similar to Template B, Template C also performs significantly worse than Template A with a 95% confidence level.

Template D: With Template D, though it shows a higher CTR than Template A, to confirm its superiority with 95% confidence, further testing might be necessary as the conclusion isn't immediately apparent.

So, the correct statement among the options provided is:

E is better than A with over 95% confidence, B is worse than A with over 95% confidence. You need to run the test for longer to tell where C and D compare to A with 95% confidence.

This means you've determined that Template E is better than A and Template B is worse than A with a high level of confidence. However, to precisely evaluate where Templates C and D stand against Template A with 95% confidence, more data or testing is needed.


Q3. You have $m$ training examples and $n$ features. Your feature vectors are however sparse and average number of non-zero entries in each train example is $k$ and $k << n$. What is the approximate computational cost of each gradient descent iteration of logistic regression in modern well written packages?

Answer:
The computational cost of each gradient descent iteration in logistic regression with sparse features can be estimated based on the number of non-zero entries in the feature vectors.

In modern well-written packages like Scikit-learn or TensorFlow, the computational complexity for logistic regression with sparse features is typically around O(m * k), where:

* m is the number of training examples.
* k is the average number of non-zero entries in each training example.
This complexity arises because, during each iteration of gradient descent, the algorithm needs to compute the gradient of the cost function with respect to each feature. With sparse features, only the non-zero entries contribute to this computation, hence the cost scales with the number of non-zero entries.

Sources:

* Scikit-learn documentation on Logistic Regression: https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html
* TensorFlow documentation on Logistic Regression: https://www.tensorflow.org/api_docs/python/tf/keras/Sequential


Q4. 4. We are interested in building a high quality text classifier that categorizes news stories into 2 categories - information and entertainment. We want the classifier to stick with predicting the better among these two categories (this classifier won't try to predict a percent score for these two categories). You have already trained V1 of a classifier with 10,000 news stories from the New York Times, which is one of 1000 new sources we would like the next version of our classifier (let's call it V2) to correctly categorize stories for. You would like to train a new classifier with the original 10,000 New York Times news stories and an additional 10,000 different news stories and no more. Below are approaches to generating the additional 10,000 pieces of train data for training V2.

a. Run our V1 classifier on 1 Million random stories from the 1000 news sources. Get the 10k stories where the V1 classifier’s output is closest to the decision boundary and get these examples labeled.

b. Get 10k random labeled stories from the 1000 news sources we care about.

c. Pick a random sample of 1 million stories from 1000 news sources and have them labeled. Pick the subset of 10k stories where the V1 classifier’s output is both wrong and farthest away from the decision boundary.
    
  Ignore the difference in costs and effort in obtaining train data using the different methods described above. In terms of pure accuracy of classifier V2 when classifying a bag of new articles from 1000 news sources, what is likely to be the value of these different methods?How do you think the models will rank based on their accuracy?

Answer:
1. Labeled Data Close to Decision Boundary from V1:

Method: Running V1 classifier on 1 million random stories and selecting 10k closest to the decision boundary.

Potential Impact: This method targets challenging examples that are difficult for the current model (V1) to classify accurately. These samples could help improve the model's understanding of nuanced cases and potentially enhance its performance on borderline instances. However, it might not cover the entire spectrum of diverse examples.

2. Random Labeled Stories from 1000 News Sources:

Method: Selecting 10k random labeled stories from the 1000 news sources.

Potential Impact: While random selection provides diversity, it might not prioritize challenging or informative samples. It could offer a broader view of the dataset but might not contribute significantly to improving the model's performance on difficult instances.

3. Misclassified Data Farthest from Decision Boundary from V1:

Method: Labeling a subset of 10k stories from 1 million where V1 output is wrong and farthest from the decision boundary.

Potential Impact: This approach focuses on the most challenging misclassified instances, potentially addressing the weaknesses of the current model. By concentrating on samples where V1 is most uncertain or erroneous, it could aid in improving the model's accuracy on difficult cases.

The effectiveness of these methods could vary based on the quality and diversity of the additional data they provide. However, based on the potential impact described:

1. Ranking based on Likely Impact on V2 Classifier's Accuracy:
* Third Approach (Misclassified Data Farthest from Decision Boundary from V1): This method could have the highest impact as it specifically targets challenging misclassified instances.
* First Approach (Labeled Data Close to Decision Boundary from V1): This method might follow, focusing on challenging examples but might not cover the entire range of cases.
* Second Approach (Random Labeled Stories from 1000 News Sources): While it provides diversity, it might contribute less to addressing the model's weaknesses on challenging instances.

Sources used to address this question:
* Understanding of machine learning model training methodologies.
* General principles of model improvement through diverse and challenging datasets.
* Notable approaches in data selection for improving classifiers.


Q5. You wish to estimate the probability, $p$ that a coin will come up heads, since it may not be a fair coin. You toss the coin $n$ times and it comes up heads $k$ times. You use the following three methods to estimate $p$
    1. Maximum Likelihood estimate (MLE)
    2. Bayesian Estimate: Here you assume a continuous distribution uniform prior to $p$ from $[0,1]$ (i.e. the probability density function for the value of $p$ is uniformly $1$ inside this range and $0$ outside. Our estimate for $p$ will be the expected value of the posterior distribution of $p$. The posterior distribution is conditioned on these observations.
    3. Maximum a posteriori (MAP) estimate: Here you assume that the prior is the same as (b). But we are interested in the value of $p$ that corresponds to the mode of the posterior distribution.
    
    What are the estimates?

Answer: The estimates for the probability $p$ that a coin will come up heads given $n$ tosses and $k$ heads using the three methods are as follows:

1. **Maximum Likelihood Estimate (MLE):**

The Maximum Likelihood Estimate for $p$ is simply the ratio of the number of heads observed to the total number of tosses. So,
$p̂_{MLE}$ = $k$ / $n$

2. **Bayesian Estimate:**

For the Bayesian approach with a uniform prior over $p$ from 0 to 1, the posterior distribution is a Beta distribution since the prior is conjugate to the binomial likelihood.
The posterior distribution of $p$ given $k$ heads out of $n$ tosses follows a Beta distribution with parameters  α = $k$ + 1 and β = $n$ − $k$ + 1. The expected value (mean) of this distribution, which serves as the Bayesian estimate for $p$, is
$p̂_{Bayesian}$ = ($k$ + 1) / ($n$ + 2)

3. **Maximum a Posteriori (MAP) Estimate:**

The MAP estimate corresponds to the mode of the posterior distribution, which is the value of $p$ that maximizes the posterior probability density function. For the Beta distribution, the mode is $p̂_{MAP}$ = $k$ / $n$, coinciding with the MLE estimate in this case.

Sources:
* For these calculations, the methodology behind Maximum Likelihood Estimation, Bayesian Estimation using a Beta distribution as a conjugate prior to the binomial distribution, and the concept of Maximum a Posteriori (MAP) estimates are fundamental concepts taught in statistics and Bayesian inference courses. Sources for these concepts and calculations can be found in various statistics textbooks and academic materials covering probability, statistics, and Bayesian inference, such as:

1. "Statistical Inference" by George Casella and Roger L. Berger.
2. "Bayesian Data Analysis" by Andrew Gelman, John B. Carlin, Hal S. Stern, David B. Dunson, Aki Vehtari, and Donald B. Rubin.
3. "Introduction to Probability and Statistics" textbooks by Sheldon Ross, William Mendenhall, Richard L. Scheaffer, among others.
