---
title: "Effects of Choice"
---

- #Selection Bias
- [Examples of selection bias in R](http://ryotamugiyama.com/2018/06/11/trancated/)([webarchve [https://web.archive.org/web/20180703030927/http://](https://web.archive.org/web/20180703030927/http://) ryotamugiyama.com/2018/06/11/trancated/]])
    - Even if there is a correlation between education and ability, education and ability can be uncorrelated in a group from which only the most able are taken.
    - <img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This text analyzes the relationship between education (deviation) and ability in terms of selection bias. The main contents are as follows
        - In the population as a whole, there is a positive correlation between deviation and ability.
        - In a group in which only highly capable individuals are selected, the correlation between deviation and ability becomes almost non-existent.
        - On the other hand, in the group in which only those with high deviation values were selected, a positive correlation between deviation values and ability was observed, as was the case in the population.
        - However, selection by deviation has the problem of reducing the variance of the independent variable (deviation) and increasing the standard error of the estimate.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Generate a Jupyter Notebook that recreates this storyline and
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>Below is a Jupyter Notebook that reproduces the contents of this article.
py

```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import statsmodels.formula.api as smf

# Setting up the simulation
np.random.seed(1)
N = 100000
ability_mean, ability_std = 0, 1
hensachi_mean, hensachi_std = 50, 10
corr = 0.3

# Sampling from a multivariate normal distribution
cov = [[ability_std**2, corr*ability_std*hensachi_std], 
       [corr*ability_std*hensachi_std, hensachi_std**2]]
ability, hensachi = np.random.multivariate_normal([ability_mean, hensachi_mean], cov, N).T

# Create data frame
df = pd.DataFrame({'ability': ability, 'hensachi': hensachi})

# Create scatter plots
plt.figure(figsize=(6, 6))
sns.scatterplot(x='hensachi', y='ability', data=df, alpha=0.5)
plt.xlabel('deviation')
plt.ylabel('ability')
plt.show()

# Selection by ability
ability_threshold = 2
df['ability_selected'] = df['ability'] >= ability_threshold

plt.figure(figsize=(6, 6))
sns.scatterplot(x='hensachi', y='ability', data=df, hue='ability_selected', alpha=0.5)
plt.xlabel('deviation')
plt.ylabel('ability')
plt.show()

# Selection by deviation
hensachi_threshold = 70
df['hensachi_selected'] = df['hensachi'] >= hensachi_threshold

plt.figure(figsize=(6, 6))
sns.scatterplot(x='hensachi', y='ability', data=df, hue='hensachi_selected', alpha=0.5)
plt.xlabel('deviation')
plt.ylabel('ability')
plt.show()

# Regression Analysis
model_all = smf.ols('ability ~ hensachi', data=df).fit()
model_ability = smf.ols('ability ~ hensachi', data=df[df['ability_selected']]).fit()
model_hensachi = smf.ols('ability ~ hensachi', data=df[df['hensachi_selected']]).fit()

print(model_all.summary())
print(model_ability.summary()) 
print(model_hensachi.summary())
```



![image](https://gyazo.com/abf389bb48d7d7a34aa1f1294885be49/thumb/1000)
:

```
                            OLS Regression Results                            
==============================================================================
Dep. Variable:                ability   R-squared:                       0.090
Model:                            OLS   Adj. R-squared:                  0.090
Method:                 Least Squares   F-statistic:                     9896.
Date:                Wed, 29 May 2024   Prob (F-statistic):               0.00
Time:                        17:04:08   Log-Likelihood:            -1.3664e+05
No. Observations:              100000   AIC:                         2.733e+05
Df Residuals:                   99998   BIC:                         2.733e+05
Df Model:                           1                                         
Covariance Type:            nonrobust                                         
==============================================================================
                 coef    std err          t      P>|t|      [0.025      0.975]
------------------------------------------------------------------------------
Intercept     -1.4885      0.015    -97.242      0.000      -1.519      -1.459
hensachi       0.0298      0.000     99.481      0.000       0.029       0.030
==============================================================================
Omnibus:                        2.020   Durbin-Watson:                   2.001
Prob(Omnibus):                  0.364   Jarque-Bera (JB):                2.011
Skew:                           0.011   Prob(JB):                        0.366
Kurtosis:                       3.006   Cond. No.                         261.
==============================================================================

Notes:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.
```


![image](https://gyazo.com/6a30ccea7cefe3cea9b3a1566d3238fe/thumb/1000)
:

```
                            OLS Regression Results                            
==============================================================================
Dep. Variable:                ability   R-squared:                       0.021
Model:                            OLS   Adj. R-squared:                  0.020
Method:                 Least Squares   F-statistic:                     48.42
Date:                Wed, 29 May 2024   Prob (F-statistic):           4.48e-12
Time:                        17:04:08   Log-Likelihood:                -761.44
No. Observations:                2282   AIC:                             1527.
Df Residuals:                    2280   BIC:                             1538.
Df Model:                           1                                         
Covariance Type:            nonrobust                                         
==============================================================================
                 coef    std err          t      P>|t|      [0.025      0.975]
------------------------------------------------------------------------------
Intercept      2.0831      0.042     49.665      0.000       2.001       2.165
hensachi       0.0050      0.001      6.958      0.000       0.004       0.006
==============================================================================
Omnibus:                      659.594   Durbin-Watson:                   2.020
Prob(Omnibus):                  0.000   Jarque-Bera (JB):             1778.136
Skew:                           1.527   Prob(JB):                         0.00
Kurtosis:                       6.062   Cond. No.                         344.
==============================================================================

Notes:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.
```


![image](https://gyazo.com/71d0b2e89f33ec93038671bfe8e9a1e1/thumb/1000)
:

```
                            OLS Regression Results                            
==============================================================================
Dep. Variable:                ability   R-squared:                       0.010
Model:                            OLS   Adj. R-squared:                  0.009
Method:                 Least Squares   F-statistic:                     22.32
Date:                Wed, 29 May 2024   Prob (F-statistic):           2.44e-06
Time:                        17:04:08   Log-Likelihood:                -3223.3
No. Observations:                2301   AIC:                             6451.
Df Residuals:                    2299   BIC:                             6462.
Df Model:                           1                                         
Covariance Type:            nonrobust                                         
==============================================================================
                 coef    std err          t      P>|t|      [0.025      0.975]
------------------------------------------------------------------------------
Intercept     -1.3937      0.441     -3.157      0.002      -2.259      -0.528
hensachi       0.0282      0.006      4.725      0.000       0.017       0.040
==============================================================================
Omnibus:                        1.860   Durbin-Watson:                   1.924
Prob(Omnibus):                  0.395   Jarque-Bera (JB):                1.804
Skew:                           0.067   Prob(JB):                        0.406
Kurtosis:                       3.030   Cond. No.                     1.59e+03
==============================================================================

Notes:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.
[2] The condition number is large, 1.59e+03. This might indicate that there are
strong multicollinearity or other numerical problems.
```


<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>The results of the three regression analyses presented can be interpreted as follows.

Analysis using overall sample (N=100,000)
- A positive relationship was found between deviation (hensachi) and ability (ability).
- An increase of one deviation increases the ability by approximately 0.03 points.
- The explanatory power of the model (R-squared) is 0.090, which is not very high.

Analysis with high ability (ability≥2) sample only (N=2,282)
- The relationship between deviation and ability is weaker than in the overall sample.
- An increase of one deviation increases the ability by only about 0.005 percentage points.
- The explanatory power of the model is quite low at 0.021.

Analysis using only the high deviation (hensachi≥70) sample (N=2,301)
- The relationship between deviation and ability is about the same as in the overall sample.
- An increase of one deviation increases the ability by approximately 0.028 points.
- However, the explanatory power of the model is very low at 0.010.

These results suggest that
- In a sample of only highly capable people, the relationship between deviation and ability becomes almost nonexistent (the effect of selection bias).
- On the other hand, the same relationship holds for the sample of only those with the highest deviation as for the total sample.
- However, selection by deviation reduces the explanatory power of the model because it reduces the sample size and the variability of the deviation.

In other words, an analysis using a sample selected by a particular attribute may not correctly capture the relationships in the population as a whole. This is especially true if the selection is made by the variable under analysis (in this case, ability).

#Statistics #Surprising Phenomena

---
This page is auto-translated from [/nishio/選択の効果](https://scrapbox.io/nishio/選択の効果) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.