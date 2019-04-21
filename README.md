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


The hypothesis is that a player's points per games can be predicted using the above predictors. 

## Tools: 

The hypothesis was tested using Jupyter Notebook and libraries such as pandas, matplotlib, numpy, seaborn, and statsmodels.

##Testing: 

The first linear regression that was made looked at the relationship between player PPG and only MPG. Using statsmodels and the ordinary least squares(OLS) function, the following results occurred: 

![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/basic_ppgmpg.PNG)

This linear model had an R Squared value of 0.787 meaning that the model accounted for 78.7% of the variability. The coefficient for MPG is 0.54 meaning as minutes per games increase the points per game increases by 0.54. The following scatterplot shows this relationship.
![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/ppgvsmpg_basic.png)

Next, the OLS function was used to predict PPG using all the predictors to see if the model can be improved and to see the effect of these other predictors. The following results occurred: 
![observations](https://github.com/AR3441/Linear-Regression/blob/master/observations/ppg_all_predictors.PNG)

The R-squared value improved to 79.8% However, this means the other predictors only accounted for 1.1% of variability. 



