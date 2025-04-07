# Problem 1

# Task 1: Simulating Sampling Distributions

## Population Distributions

Select several types of population distributions, such as:

- Uniform distribution
- Exponential distribution
- Binomial distribution

For each distribution, generate a large dataset representing the population.

### Formulas:

1. **Uniform Distribution**:  
   The uniform distribution has the following probability density function (PDF):  
   $$ f(x) = \frac{1}{b - a}, \quad a \leq x \leq b $$  
   where $a$ and $b$ are the minimum and maximum values of the distribution, respectively.

2. **Exponential Distribution**:  
   The exponential distribution has the following PDF:  
   $$ f(x) = \lambda e^{-\lambda x}, \quad x \geq 0 $$  
   where $\lambda$ is the rate parameter, which is the inverse of the mean.

3. **Binomial Distribution**:  
   The binomial distribution has the following probability mass function (PMF):  
   $$ P(X = k) = \binom{n}{k} p^k (1-p)^{n-k} $$  
   where $n$ is the number of trials, $k$ is the number of successes, and $p$ is the probability of success in a single trial.

# Task 2: Sampling and Visualization

## Sampling Data

Randomly sample data from the population and calculate the sample mean for different sample sizes, such as 5, 10, 30, and 50.

- **Sample Mean**: The sample mean is given by the formula:  
  $$ \bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i $$  
  where $\bar{x}$ is the sample mean, $n$ is the sample size, and $x_i$ are the individual sample points.

Repeat the process multiple times (e.g., 1000 iterations) to create a sampling distribution of the sample mean.

### Visualization

- Plot histograms of the sample means for each sample size (5, 10, 30, 50).
- Observe how the histograms converge to a normal distribution as the sample size increases, illustrating the Central Limit Theorem (CLT).
