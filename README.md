# Exploration of Quantitative Finance

Alongside my study of Econometrics and Data Science at the University of Amsterdam, I enjoy exploring quantitative finance in my spare time. By applying the mathematics, financial and statistics skills that are taught at the UvA (and beyond), I get to explore the real-world applications of what is taught. I plan to keep adding new projects to this repository, while also keeping up with the courses at the UvA. All code is written in Python 3.13. Questions and ideas are welcome, so feel free to get in touch via [LinkedIn](https://www.linkedin.com/in/thijs-van-de-leemkolk-1abbb2398/).
## Projects
 
### 00 - Efficient Frontier
 
This project optimises the allocation of my personal four-ETF portfolio using the *efficient frontier*. Using this method, I created efficient portfolios, which maximise expected return at a certain level of volatility. Using historical data, the annualised mean returns and covariance matrix can be found. By simulating thousands of random (long) portfolios, using the Dirichlet distribution, a graph can be plotted in which all possible portfolios are visualised, together with their historical return and volatility. By using mathematical methods, the following formulas (weights $w$, expected returns $\mu$ and covariance matrix $\Sigma$) can be found for the minimum-variance and maximum Sharpe ratio portfolio:

$$ \mu_p = w^\top \mu \qquad \sigma_p^2 = w^\top \Sigma w \qquad S_p = \frac{\mu_p - r_f}{\sigma_p} $$
 
$$ \min_{w} \; w^\top \Sigma w \qquad \max_{w} \; \frac{w^\top (\mu - r_f \mathbf{1})}{\sqrt{w^\top \Sigma w}} \qquad \text{subject to } w_i \geq 0, \; w^\top \mathbf{1} = 1 $$
 
 Because of the long-only constraint $w_i \geq 0$, these problems have no closed-form solution and are solved numerically using `scipy.optimize`. Since my own portfolio was not efficient, I also found the highest-return portfolio for a given level of volatility.  When looking at the results, it would be beneficial to lower the percentage of EMIM and TEET and increase the percentage of CSPX in the portfolio. When re-evaluating my portfolio, these results should be evaluated accordingly. It is important to not be blindsided by focusing solely on the *efficient frontier*, other measures should also be taken into account.

 ![Efficient frontier](images/00_0.png)
 ![Table](images/00_1.png)

 
## Disclaimer
 
This repository is for educational purposes only and is not financial advice.
 
---
