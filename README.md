# stochastic_intervention
Code to replicate stochastic intervention on ACE scores across racial groups


1. First, we use the estimated beta coefficients and variance-covariance matrix from our outcome model to generate a single resampled value of the beta coefficients from a multivariate normal distribution (37–39).
2. We then resample covariate values with replacement m times from one imputed data frame, where m = number of observations in the dataset. We use these resampled data to get the distribution of covariates under no intervention.
3. We use the coefficients sampled in step 1 to obtain the predicted probability of anxiety for each observation, and then sum across all observations to estimate the race-specific prevalence of anxiety under no intervention.
4. Next, we create a copy of the resampled data from step 2, replacing the ACEs score for all non-White participants with simulated value from a Poisson distribution, with the rate parameter estimated from a Poisson model fit among White participants.
5. We repeat step 3 to calculate the prevalence of anxiety in this single draw from the intervention distribution.
6. We calculate the risk differences by race as the averaged risk differences across each observation in the various racial groups from the resampled population.
7. Finally, we repeat this procedure 1,000 times to build up the sampling distribution of the race-specific RD. From these 1,000 resampled estimates, we report median differences as race-specific point estimates and quantile-based 95% uncertainty intervals around the risk differences.
![image](https://user-images.githubusercontent.com/8146267/230487986-2002ab4e-75e1-4372-9c3c-02d432ff1627.png)
