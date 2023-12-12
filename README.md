# Contlo_Assignments_2023
Two types of Assignments are provided by Contlo:
1. Q/A Assignment which consists of 5 questions and its answers
2. Coding Assignment where I am implementing and optimizing GPT-2 Model

# Q/A Assignment
1. You train Logistic Regression with a certain set of features and learn weights $w_0$, $w_1$ till $w_n$.
Feature $n$ gets weight $w_n$ at the end of training. Say you now create a new dataset where you duplicate feature $n$ into feature $(n+1)$ and retrain a new model. Suppose this new model weights are $w_{new_0}$, $w_{new_1}$ till $w_{new_n}$, $w_{new_{n+1}}$. What is the likely relationship between $w_{new_0}$, $w_{new_1}$ , $w_{new_n}$,  and $w_{new_{n+1}}$?

Answer:
When you duplicate feature $n$ into feature $(n+1)$ and retrain a new model, the weights of the original feature $n$ and the duplicated feature $(n+1)$ might change due to the model's optimization process. However, the relationship between these weights is not straightforward and can vary depending on multiple factors such as the nature of the data, regularization techniques used, and the convergence of the optimization algorithm.

In general, the weights $w_{new_n}$ and $w_{new_{n+1}}$ for the duplicated features might not necessarily be the same as $w_n$ and could differ significantly. The exact relationship between $w_{new_0}$, $w_{new_1}$, $w_{new_n}$, and $w_{new_{n+1}}$ cannot be determined without analyzing the specific data and the model training process.

When duplicating a feature and retraining the model, the new weights are likely to be influenced by interactions with other features, potential multicollinearity issues between the duplicated features, and the way the model adapts during training.

Sources used:

Hastie, T., Tibshirani, R., & Friedman, J. (2009). The Elements of Statistical Learning: Data Mining, Inference, and Prediction. Springer Science & Business Media.
Bishop, C. M. (2006). Pattern Recognition and Machine Learning. Springer.
