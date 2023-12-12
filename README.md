# Contlo_Assignments_2023
Two types of Assignments are provided by Contlo:
1. Q/A Assignment which consists of 5 questions and its answers
2. Coding Assignment where I am implementing and optimizing GPT-2 Model

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
