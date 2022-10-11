# VaR-Model
Basic Value at Risk Model. I approach this in 2 different ways: Variance-Covariance Method &amp; Monte Carlo Simulation Method
# High-Level Overview - Variance-Covarience Method
Preliminary steps: Pick options and set weights

1. Build Hypothetical Portfolio and Calculate Avg returns
	- Download stock Data: Get 'Adj Close' for each option throughout a specific time frame. 
	- Calculate Daily Returns, Get Average returns.
	
2. 	Make Variance-Covariance Matrix & Calculate Portfolio Risk (Standard Deviation), Portfolio Expected Return
	- Build Cov Matrix from returns
	- Calculate Expected Portfolio Return: Average Return * weights
	- Calculate Expected Variance = Weights(Transpose) * (Covariance Matrix) * Weights
	
3. Build Normal Distribution Curve
	- Define x axis with evenly spaced numbers. 
	- Probability density function parameters = X axis, Portfolio Mean, Portfolio STD
	- Visualize with Matplotlib
	
4. Calculate VaR & Confidence Interval
	- At 0.05 Confidence
	- Percent Point Function parameters = confidence level, portfolio mean, portfolio standard dev
	
	

# Brief Background on VaR metric

Definition
- A Metric that estimates the amount of financial risk in a given portfolio over a specific time frame. 

Properties of VaR Calculation:
- The value returned is the maximum loss amount
- Can be calculated at varying confidence intervals (ex: 90,95) 
	
Benefits of VaR:
- Long term Capital Growth, Risk Managment
	
How to read VaR metric:
- Example: A portfolio has a VaR of 350,000 USD over the next month at 95% confidence.
- Interpretation: With 95% confidence, we can say that the portfolio's loss will not exceed 350,000 USD in a month.
		
Ways of calculating VaR

1.  Monte Carlo Simulation (Conditional VaR)
	- Random scenarios for future rates are created (using non-linear pricing models) to estimate the change in value for each scenario, then calculating the VaR according to the worst losses.
	- It assumes that there is a known probability distribution for risk factors.
	
2.  Variance-Covariance Method (Parametric Method)
	- Assumes a normal distribution in returns
	- 2 factors are to be estimated: 1) Expected Return (mean) 2) Standard Deviation (Portfolio Risk)
	- This method is best for problems with known and reliable distribution estimates. 
	- Not a good method for problems with a small sample size. 
	- Equation: 
		- ![image](https://user-images.githubusercontent.com/84755881/195148992-cf055376-fbb0-4aa4-9675-1eb0275ed2f7.png)

		
