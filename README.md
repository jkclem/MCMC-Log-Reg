# MCMC-Log-Reg
Contains a class that fits logistic regression parameters via a modified Metropolis-Hastings algorithm.

Requires numpy, scipy, and tqdm libraries.

Possible inputs are:
    
     y: numpy array (column vector) of the training labels; length must match the number of rows in X
    
     X: numpy array (matrix format) of independent variables
    
     beta_priors: numpy array of the prior beliefs for each coefficient in the model;
                  must be the same length as the number of columns in X matrix or one more if adding an
                  intercept
    
     prior_stds: numpy array of the standard deviations of the priors;
                 must be the same length as the beta_priors
    
     jumper_stds: numpy array of standard deviations of the jumping distribution for each beta coefficient;
                  must be the same length as beta_priors
    
     num_iter: an int for the number of interations to perform
    
     add_intercept: True (default) if the user wants to add an intercept to X
    
     random_seed: int that sets the random seed for reproducibility
    
     alpha: float on the closed interval 0 to 1:
            used to create the (1 - alpha)*100% credible interval for the coefficients
    
     burn_in: float on the closed interval 0 to 1:
              it is the proportion of simulate coefficients to discard as the algorithm searches the parameter space
    
