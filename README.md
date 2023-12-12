# Contlo_Assignments_2023
Two types of Assignments are provided by Contlo:
1. Q/A Assignment which consists of 5 questions and its answers
2. Coding Assignment where I am implementing and optimizing GPT-2 Model

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
