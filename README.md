# Linear-Regression: NBA Points Per Game 

## Introduction:

  In this project, the relationship between player points per game, minutes per game and other player statistics was evaluated. The data used in this project contained season totals in points, minutes, games played, team pace as well as other data about the player's position, age, height and weight from the 1996-1997 season to the 2016-2017 season. The raw data was retrieved from datasets on Kaggle and from the NBA website. The data after being cleaned contained 8045 players.
  
## Hypothesis:

The question being asked is to what extent can player points per game be predicted using a linear regression model. The main predictors being checked were: 
- player minutes per game
- player position 
- team pace(# of team possessions of the ball in 48 minutes)
- an interaction between height and weight
- interaction between player age and what year in career 


The hypothesis is that a player's points per games can be predicted using the above predictors. These were chosen because they had some correlation with player points per game. The predictors, height and weight correlated with each other, so they were made into one interaction by multiplying them. The same was done for age and career year. This can be seen when looking at a heatmap, to see which variables are correlated. 

![observation](https://github.com/AR3441/Linear-Regression/blob/master/observations/heatmap.png)

## Tools: 

The hypothesis was tested using Jupyter Notebook and libraries such as pandas, matplotlib, numpy, seaborn, and statsmodels.

##Testing/Analysis: 

The first linear regression that was made looked at the relationship between player PPG and only MPG. Using statsmodels and the ordinary least squares(OLS) function, the following results occurred: 

![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/basic_ppgmpg.PNG)

This linear model had an R Squared value of 0.787 meaning that the model accounted for 78.7% of the variability. The coefficient for MPG is 0.54 meaning as minutes per games increase the points per game increases by 0.54. The following scatterplot shows this relationship.
![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/basicmodelvsdata.png)

Next, the OLS function was used to predict PPG using all the predictors to see if the model can be improved and to see the effect of these other predictors. The following results occurred: 
![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/ppg_all_predictors.PNG)

The R-squared value improved to 79.8% However, this means the other predictors only accounted for 1.1% of variability which can also be seen when examining the coefficients for those predictors. The coefficient for MPG is about the same while the coefficient for the other predictors are very low. The coefficients 'PG', 'SG', 'SF', and 'PF' are also dummy variables are inrelation to the variable 'C' which is dropped.  One thing that did change was the y-intercept. But overall, a player's MPG seems to be the biggest predictor of a player's PPG. This isn't surprising given the heatmap seen earlier, but to better understand the accuracy of the model, a residual plot is done. 

![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/residualsplot.png)
Looking at this graph, the residuals are not randomly distributed meaning the model is better in some areas than in other areas. In this situation, the residuals increase as the predicted PPG increases. To better understand why this may be happenning, the distribution of player PPG was looked at. 

![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/ppg_distribution.png)

The distribution of PPG is very skewed and most of the player's in this data set have scored around 5 points per game. I wanted to see how the model would change when looking at data for player's that only scored more than 10 points per game. It should also be noted that players that score more than 10 points per game account for 2856 players out of our 8045 players.The following results were occcured:

![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/ols_morethan10ppg.PNG)

The R squared value decreased a lot and know only accounts for 51.9% of the variability. The coefficient for MPG increased as well as the coefficients for 'HeightxWeight' and 'agexcareer'. However, it seems that MPG is still the biggest predictor.  

## Conclusion

The graph below, shows the original model with only MPG as a predictor with cut offs at 10 PPG and 20 PPG. 

![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/cutoff20.png)

It is very easy to see here and the residual plot from before, that the model doesn't do as well when predicting as MPG increased. The model accounted for 79.8% of the variability but this decreased to 51.9% when looking at players that scored over 10 PPG. However, this is 2856 out of the 8045 players that were originally in the set. Looking at the original set, it can be said that player MPG is a good predictor of player PPG since most players do score less than 10 PPG. However, improvements need to be made to the predictive model to account for player's that are scoring more. This can be done by finding other predictors that better correlate to player PPG or by using a polynomial regression. 










