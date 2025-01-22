## Maximum Likelihood

For independent and identically distributed (i.i.d.) data $X = {x_1, x_2, ..., x_n}$, the likelihood function is the joint probability of the data: 
$L(\theta | \mathbf{x}) = \prod\limits_{i=1}^{n} P(x_i | \theta)$. 

The log-likelihood is usually used because? 
$\ell(\theta | \mathbf{x}) = \log L(\theta | \mathbf{x}) = \sum\limits_{i=1}^{n} \log P(x_i | \theta)$

Maximum likelihood is finding the parameter $\theta$ that maximizes the log-likelihood
$\hat{\theta} = \arg\max \limits_{\theta} \ell(\theta | \mathbf{x})$




