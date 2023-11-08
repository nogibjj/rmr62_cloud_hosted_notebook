# Cloud Notebook Demo
### by Rakeen Rouf

[![PythonCiCd](https://github.com/nogibjj/rmr62_cloud_hosted_notebook/actions/workflows/python_ci_cd.yml/badge.svg)](https://github.com/nogibjj/rmr62_cloud_hosted_notebook/actions/workflows/python_ci_cd.yml)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/gist/rmr327/99704d2d80c3a4718e7bd31cf9f4acd9/cloudnotebookdemo.ipynb)


---

**Summary**

This repo shows how we can host a cloud notebook, and perform simple data analyses on it. For this demo, I host a note book on google colab, and share it using a github Gist. A GitHub gist is a simple way to share code snippets, text, or other information with others. It's a Git repository that can contain one or more files, but it's not a full-fledged project. Gists are typically used for sharing small pieces of code or text that don't warrant the creation of a full repository.

---
## **Code Overview**

#### Ingest

In the ingest section, I retreive player stats from the nba_api from 2000 to 2023. We will then go through some EDA, and finally fit a Linear Regression inference model to fit total points scored by players in a season.

![image](https://github.com/nogibjj/rmr62_cloud_hosted_notebook/assets/36940292/6386ff87-0a79-4fcf-a77c-5f8a23b3250d)

#### EDA
The EDA section shows some descriptive statistics for our dataset, and explores the relationships between some variables through informative plots.

- The points histogram follows a distribution with a right skew, and appears to be exponential/poisson in nature.
- The age distribution of the players in the last 13 seasons of the nba appear to follow a normal curve, with a mean aroun 25.
- The average points by age also seems to follow a normal distribution with players scoring the most points in the 25-30 age group.

![image](https://github.com/nogibjj/rmr62_cloud_hosted_notebook/assets/36940292/dec2f36c-b6cf-4284-9f47-6dafd9d30576)
![image](https://github.com/nogibjj/rmr62_cloud_hosted_notebook/assets/36940292/9b91e40a-fdde-428c-83f7-259d22d389a2)

#### Modeling & Conclusion
![image](https://github.com/nogibjj/rmr62_cloud_hosted_notebook/assets/36940292/787af7e6-3c3b-4e0d-8ebf-7682c1b5250a)

The R-squared value of 0.979 indicates that the model explains 97.9% of the variance in the dependent variable (PTS). This suggests that the linear regression model is a good fit for the data.

The coefficients for the independent variables (AGE, MIN, and FGA) indicate the direction and strength of the relationship between each variable and the dependent variable (PTS).

The coefficient for AGE is -0.1306, which means that, holding all other variables constant, a one-year increase in age is associated with a decrease of 0.1306 points per game. However, the p-value for AGE is 0.377, which is not statistically significant at the 0.05 level. This suggests that age may not have a significant effect on points per game after controlling for the other variables in the model.

The coefficient for MIN is -0.0049, which means that, holding all other variables constant, a one-minute increase in playing time is associated with a decrease of 0.0049 points per game. The p-value for MIN is 0.012, which is statistically significant at the 0.05 level. This suggests that playing time has a significant effect on points per game after controlling for the other variables in the model.

The coefficient for FGA is 1.2722, which means that, holding all other variables constant, a one-shot increase in field goal attempts is associated with an increase of 1.2722 points per game. The p-value for FGA is 0.000, which is statistically significant at the 0.05 level. This suggests that field goal attempts have a significant effect on points per game after controlling for the other variables in the model.

The intercept of -10.5786 represents the expected value of PTS when all independent variables are equal to zero. However, since none of the independent variables can actually be zero in this context, the intercept is not particularly meaningful.

The R-squared value and the p-values for the independent variables suggest that the model is a good fit for the data and that MIN and FGA are significant predictors of PTS, while AGE may not be a significant predictor after controlling for the other variables in the model. However, it's important to note that this interpretation is based on the assumption that the model meets the underlying assumptions of linear regression, such as linearity, normality, and homoscedasticity. These assumptions should be checked before drawing any conclusions from the model.
