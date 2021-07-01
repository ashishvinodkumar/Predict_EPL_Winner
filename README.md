# Predict English Premier League (EPL) Winner

Full Report: https://github.com/ashishvinodkumar/Predict_EPL_Winner/blob/main/20_Report/IDS-702-Final-Project-Report.pdf

# Goal
The goal of this project is to predict who is going to win the 2015-2016 english premier league season, along with identifying key features that influence a team’s ability to win the league. The report details building a hierarchical linear regression model, to account for all necessary predictors and any potential interactions that would improve the prediction ability of the model. The main takeaway from this report will be to assess the key features, and prediction accuracy of the model.

# Background 
English Premier League is the top soccer league in England which is contested by 20 teams each season. Each of these 20 teams play the other teams twice, once at their home stadium and once at their opponent’s home stadium (usually referred to as ‘away’). A win in a match between 2 teams results in 3 points, a draw results in 1 point, and a loss results in 0 points. As teams play each of the other teams in a round robin fashion, an official points table gets updated after each game to keep track of who is currently leading the points tally. At the end of the season, the team with the most points, is crowned champions of the english premier league for that given season. In this race to first place in the premier league, a team’s attributes such as defensive style, whether they press high up the pitch or sit deep in their own half, passing style, whether they make long diagonal passes or short and quick passes, and chance creation, whether a team is creating enough chances to score goals in the final third of the pitch, and many more such predictors determine the quality of the team throughout the entire season. I aim to incorporate all of these predictors to answer the following questions:

●	What are the key features that influence a team’s ability to win an english premier league season?

●	Assess the hierarchical linear regression model’s prediction accuracy both in-sample and out-of-sample. 

For the out-of-sample prediction, the report details predicting the winner of the 2015-2016 EPL season and comparing the result against the expected/actual winner.


# Exploratory Data Analysis (EDA)
The most notable EDA was the interaction between ChanceCreationCrossing and buildUpPlayPassing. ChanceCreationCrossing determines the number of times in the entire season that a given team creates a goal scoring chance by crossing the ball into their opponent’s half. BuildUpPlayPassing signifies the style of play leading up to a chance, ranging from long diagonal passes, mixed balls (combination of long and short passes), and short passes.

![interaction_epl](https://user-images.githubusercontent.com/26104722/124060689-8e28f680-d9fb-11eb-9477-8fcaff76bccd.png)

As you can see in the above plot, for both long and mixed BuildUpPlayPassing levels, as the ChanceCreationCrossing increases, the overall win percentage also increases. However, when BuildUpPlayPassing is Short, and as the ChanceCreationCrossing increases, the overall win percentage decreases. I took note of this interesting interaction, to further analyze if this trend is statistically significant in the Model Selection section.

# Model Selection
For a detailed model selection and explanation, please refer to the pdf report.
<img width="1422" alt="epl_model" src="https://user-images.githubusercontent.com/26104722/124060688-8e28f680-d9fb-11eb-8fe8-0ace9f9ab563.png">


# Conclusion
Using the hierarchical linear regression model, this report tried to explore and identify the key predictors that influence the overall win percentage for a team. The analysis identified BuildUpPlayPassing, DefencePressure, DefenceAggression, ChanceCreationPassing, and the interaction between DefenceAggressionClass and ChanceCreationPassing as significant predictors that influence a team’s ability to win the premier league season. I also sought to perform an out of sample prediction with predicting the winner of the 2015-2016 season. My model predicted Arsenal to have the highest overall win percentage, and given the unpredictability of the 2015-2016 season and Leicester City’s meteoric rise, the model predicted reasonably well by selecting Arsenal, the next best team as champions for the 2015-2016 season. However, I would argue that there are limitations to the model. Firstly, only 6 years of data ranging from 2009-2015 is not sufficient to make reliable predictions. Also, by retaining teams that only appear at least 4 times in the dataset, it eliminates teams like Leicester City. Also, it would be beneficial to include season-wide player ratings as certain ‘star’ players would consistently have a higher rating, thus positively impacting the team’s overall performance. In all, there was insufficient data to further improve the model. To conclude, this analysis only serves as a preliminary insight and there remains room for improvement.



