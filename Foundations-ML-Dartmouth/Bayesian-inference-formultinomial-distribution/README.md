Bayesian Inference for the Multinomial Distribution
In this exercise, you will write your own Python code to perform two instances of Bayesian update.

Bayesian Update
Recall that Bayes' rule states that a posterior probability is proportional to the product of the likelihood and the prior, such that: 𝑝𝑜𝑠𝑡𝑒𝑟𝑖𝑜𝑟∝𝑙𝑖𝑘𝑒𝑙𝑖ℎ𝑜𝑜𝑑×𝑝𝑟𝑖𝑜𝑟
.

The Prior
Let's say we have some data from a previous experiment that we base as our prior. If we have some prior distribution on 𝜇
 taking the form of a Dirichlet distribution, the prior, 𝑝(𝜇⃗ |𝛼⃗ )=𝐷𝑖𝑟(𝜇⃗ |𝛼⃗ )
, is equal to Γ(𝛼0)Γ(𝛼1)...Γ(𝛼𝐾)∏𝑘=1𝐾𝜇(𝛼𝑘−1)𝑘
. Here, the hyperparameters 𝛼⃗ 
 are counts of the number of 1
's and 0
's generated in a prior Multinomial trial of 𝑁𝑝𝑟𝑖𝑜𝑟
 samples. So for example, if we rolled 30d4 and found that we got 12 ones, 4 twos, 8 threes, and 6 fours, then we would establish that 𝐾=4
, 𝛼1=12
, 𝛼2=4
, 𝛼3=8
, and 𝛼4=6
. Here, 𝑁𝑝𝑟𝑖𝑜𝑟=𝛼0=∑𝑘=1𝐾𝛼𝑘
.

The Likelihood
Now let's consider the likelihood term, which captures new information. Let's say we perform a new experiment and get new data (new information). We roll another 𝑁𝑙𝑖𝑘𝑒𝑙𝑖ℎ𝑜𝑜𝑑=10
 d4. In this trial, there were an additional 𝑚1=4
 ones, 𝑚2=1
 twos, 𝑚3=3
 threes, and 𝑚4=2
 fours. 𝑁𝑙𝑖𝑘𝑒𝑙𝑖ℎ𝑜𝑜𝑑=∑𝑘=1𝐾𝑚𝑘=4+1+3+2=10
. The parameters 𝑚𝑘
 captures the number of 1
's of each class or "bin" in this new data set.

The likelihood, 𝑝(𝜇⃗ |𝑚⃗ ))
, is given by 𝑀𝑢𝑙𝑡(𝑚1,...,𝑚𝐾|(𝜇⃗ ,𝑁))=(𝑁𝑚1𝑚2...𝑚𝐾)∏𝑘=1𝐾𝜇𝑚𝑘𝑘
.

The Posterior
The posterior, 𝑝(𝜇⃗ |(⃗ ,𝛼⃗ ))
 takes on the form of the prior, because the Dirichlet distribution is a conjugate prior! We can use this for sequential estimation. Here the term ⃗ 
 captures the new data. 𝑚⃗ 
 captures the counts of each class in ⃗ 
.

In the video, Peter showed that the posterior is given by:

𝑝(𝜇⃗ |(⃗ ,𝛼⃗ ))=Γ(𝛼0+𝑁)Γ(𝛼1+𝑚1)...Γ(𝛼𝐾+𝑚𝐾)∏𝑘=1𝐾𝜇𝛼𝑘+𝑚𝑘−1
,

which does indeed take on the form of a Dirichlet distribution.

Bayesian Update
Using the expression for the posterior, we can write a function that can do sequential estimation. In this lab exercise, you will visualize this for the case of 𝐾=3
, but you should think about how this analysis could be extended to, say, 𝐾=6
, or 𝐾=10,000
.

Visualizing the Bayesian Update
In this part of the lab, assume 𝐾=3
. Implement Bayesian update for the Dirichlet distribution with the following iterations and plot the response.

Iteration 0:
We start by forming our prior:

𝑚⃗ =[3,3,15]
.

Iteration 1:
We get new data to incorporate into our model:

𝑚⃗ =[4,30,2]
.

Iteration 2:
We get one final set of new data to incorporate into our model:

𝑚⃗ =[55,3,5]
.

Instructions
Rather than trying to plot the distribution on the same set of axes, we will use three sub plots to visualize the data. Please use the starter code provided for plotting. You should also refer back to the previous assignment, where you visualized the Dirichlet distribution for your reference. You are welcome to use any of the code you would like there.
