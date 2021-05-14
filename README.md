# LR_NBAProject

## Predicting FanDuel NBA Score using Regression Models

### Abstract

You are part of a daily fantasy betting group that wants to win money playing Fanduel tournaments. In order to win money you have to score in the top 23% amongst tens of thousands. To do so, the main goal is to have an understanding of which players will score well during that particular day. A Fan Duel score is made up of  
8 offensive and defensive categories. To predict the Fan Duel score, I used the idea of how a player is either on offense or defense to capture features that can provide an insight of what a player specializes in. The general procedure was to webscrape Nba data that is relevant to that idea, clean out the data that I don't need and prepare it for analysis. My exploratory analysis revealed that the features had linear relationships with the target Fan Duel score, so I could apply regression models. Fortunately, my final model was able to predict relatively close to the target Fan Duel score of an active player with a mean absolute error of 5, meaning your fantasy group would benefit from using this model to establish a baseline prediction for your players.

### Design

<div>
<center>FanDuel's current scoring table as of 5/6/21 </center><br>

| FGM | FTM | 3PM | REB | AST | STL | BLK | TO | 
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| 2 | 1 | 1 | 1.2 | 1.5 | 3 | 3 | -1 |
</div>    

To predict the Fan Duel score, I thought of the stats as measurements of a player's specialities. There are other contributing variables like momentum and the opponents defensive strengths. The main feature focus was to identify the player's tendencies and attributes that impact the way they act on the court. Good defensie does not mean high steals or blocks rates, those stats are left to the players with tendencies to go for steals and blocks. A player's tendencies on court is impacted by their attributes like are injuries. There is a momentum factor where a player could perform above their mean for a period of time.

Using this structure, I picked out features that are related and designed features like rest days and hot streaks to enhance the predictive powers of my model. 

### Data

I collected team statistic, team roster, a list of players who played in a certain season and player box score data from Basketball reference for two seasons in 2017-2018 and 2018-2019. The reasons for this is the NBA transition from a league where centers dominated to one that is faster pace and easier for guards to score around 2015. I avoided the seasons in 2020 and 2021 because of the amount of missing and canceled games.  

### Algorithmn 

I split and scored my features and target with a simple train, test split to check for fit. The model had almost equal training R2 and testing R2 scores above .65 so I did not do any regularization. I did a cross validation to check the R2 scores and it was consistent. The MAE was close to 6 which was okay since the target range is 99. There was room for improvement because a scatter plot of the predicted y and actual y showed a curve which meant the data could be curving at some points. Fitted the data to a polynomial of 2nd degree increased the R2 score by 7 and lowered the MAE to 5. I did a cross validation of this model and it was consistent so I kept it as my final model.

### Conclusion

For my stakeholders I randomly sampled a player to predict his score with the final model and it was less than one point away from the actual. This is great news for your fantasy sports group's goal to have a baseline prediction. I plan on adding more features in the future to lower the mean absolute error and to incorporate the salary data from FanDuel to help you find budget picks. 

### Links

[Final Code]
[Presentation]
[Write Up]
