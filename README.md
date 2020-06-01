# Bayesian-Optimization

Many optimization problems in Machine learning are black-box problems where the objective function f(x) is a black-box.Evaluation of the function is restricted to sampling at a point x and getting a possibly noisy response.
It becomes easy to evaluate the function if the data points are ver less or the dimension seems to be low using the standard adn powerful search technique's like Random search which randomnly searches the hyperparameter domain space and output the best hyperparameter which optimizes the function.

Bayesian Optimization is a powerfull technique when it comes to evaluate the objective function on a high dimensional data set(large number of variables) or the sample performance takes a long to evaluate.

This is the domain where Bayesian optimization techniques are most useful. They attempt to find the global optimimum in a minimum number of steps. Bayesian optimization incorporates prior belief about f and updates the prior with samples drawn from f to get a posterior that better approximates f. The model used for approximating the objective function is called surrogate model. Bayesian optimization also uses an acquisition function that directs sampling to areas where an improvement over the current best observation is likely.

# Surrogate Model 

A popular surrogate model for Bayesian optimization are Gaussian processes (GPs).GPs define a prior over functions and we can use them to incorporate prior beliefs about the objective function (smoothness, …). The GP posterior is cheap to evaluate and is used to propose points in the search space where sampling is likely to yield an improvement.

# Acquisition Function

Proposing sampling points in the search space is done by acquisition functions. They trade off exploitation and exploration. Exploitation means sampling where the surrogate model predicts a high objective and exploration means sampling at locations where the prediction uncertainty is high. Both correspond to high acquisition function values and the goal is to maximize the acquisition function to determine the next sampling point.Expected imrovement acquisition function used to formalize what constitutes a "best guess".

# Approach 

In this approach we would be dealing with 4 parts:
* Optimizing the objective function (Minimizing the validation error)
* Domain Space - Set of Hyperparameters space
* Optimization algorithm - Surrogate model to find the next best point to evaluate the model.
* Storing the outcomes from the evaluation of the objective function consisting of hyperparameters and validation error.

# Libraries used 

There are multiple libraries available based on the acquisition functions. Some of them are listed below.

* Hyperopt (using TPE : Tree parzen estimator) Our focus will be using this.
* Spearmint (GP Surrogate)
* SMAC (Random Forest regression)

Detail of the algorithms can be find here : https://papers.nips.cc/paper/4443-algorithms-for-hyper-parameter-optimization.pdf
