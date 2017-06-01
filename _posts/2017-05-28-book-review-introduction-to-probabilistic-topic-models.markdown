# Introduction to Probabilistic Topic Models
 David M. Blei, Princeton University, http://menome.com/wp/wp-content/uploads/2014/12/Blei2011.pdf
 
## On smoothing and inference for topic models
 A. Asuncion, M. Welling, P. Smyth, and Y. Teh. On smoothing and inference for topic models. In Uncertainty in Artificial Intelligence, 2009.
 
## A collapsed variational Bayesian inference algorithm for latent Dirichlet allocatio
 Y. W. Teh, D. Newman, and M. Welling. A collapsed variational Bayesian inference algorithm for latent Dirichlet allocation. In NIPS 19, pages 1353–1360. 2007
 

Parameters | Maximize | Sample | Assume independent | Marginalize out
------------ | -------------| ------------ | ------------- | -------------
Maximize | Viterbi EM | ? | ME | ME
Sample | Stochastic EM | Gibbs sampling | ? | collapsed Gibbs
Assume independent | Variational EM | ? | VB | CVB
Marginalize out | EM | MCMC | EP for LDA | Intractable

## Parameter estimation for text analysis
 Gregor Heinrich 
