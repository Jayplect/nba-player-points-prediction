# NBA Player Statistics Analysis and Prediction System

## Background
Basketball is a popular team sport played on a rectangular court between two teams, each consisting of five players. The objective of the game is to score points by shooting a ball through the opponent's hoop while preventing the opposing team from scoring.

## Project overview
Our goal in this project was to attempt to predict the points for basketball player for the upcoming season using machine learning techniques. The system utilizes historical NBA player data that includes various features to provide insights into player performance and predict the player points for the upcoming season. These features include factors such as points, assists, rebounds, shooting percentages, and more relevant statistics. A dashboard was built to display the results using Tableau. Click <a
href="https://public.tableau.com/app/profile/sri.hari.priya.maringanti/viz/Project4NBAPlayerpointspredictionLeaderboard/PlayerStatsPrediction#1">here</a> to view dashboard

## Objectives
- Leverage player stats from the previous year to forecast player performance.
- Identify suitable machine learning algorithms for scalability, accuracy, and interpretability in predicting player performance.
- Evaluate the performance of the prediction system and ensure its effectiveness in real-world scenarios, such as team selection and player scouting.

## Approach
Our approach consisted of data collection, data preprocessing, feature selection, train-test splitting the data, model training and selection, model evaluation and then prediction.

## Project Steps
### Data Collection
Prior to formulating a strategy for training and testing classifiers, the collection of relevant data had to take place. NBA player statistics datasets were retrieved from Kaggle for <a href ="https://www.kaggle.com/datasets/vivovinco/nba-player-stats">2021/2022</a> and <a href = "https://www.kaggle.com/datasets/vivovinco/20222023-nba-player-stats-regular?select=2022-2023+NBA+Player+Stats+-+Regular.csv">2022/2023</a> season. Both datasets contained player statistics for their respective season.
The dataset containing the player statistics was stored in an RDS (Relational Database Service) database. By housing the player stats dataset in an RDS database, it provides a centralized and structured storage system for the data.

For the player headshot, we utilized a technique called web scraping to gather images of player headshots from the <a href = "https://www.nba.com/players/">NBA website</a> and <a href = "https://loodibee.com/nba/">other sources</a>.This was done in compliance with legal and ethical guidelines, respecting website terms of service.

### Data Preprocessing 
Our second step involved identifying null values in a dataset and implementing strategies to handle them. This typically includes dropping rows or columns with null values. The goal is to ensure that the dataset is free from null values, enabling accurate and reliable data analysis and modeling.

### Exploratory Data Analysis: 
To gain some insights on the dataset patterns we created a visualization to show the distribution of points per team (Fig 1.) and a scatter plot to show the minutes played per points (Fig 2.) for the entire 2022/2023 season. 

- Fig 1. Bar plot of Average Points per Team for 2022/2023 Season

![image](https://github.com/Jayplect/credit-risk-classification/assets/107348074/c92f86ab-d928-48c2-a367-b4d7df502e28)

- Fig 2. Scatter plot of Minutes Played and Points

![image](https://github.com/Jayplect/credit-risk-classification/assets/107348074/b43089c2-3c7b-46a9-b7ca-a6245d609af0)

### Model Training and Evaluation
We experimented with various regression models such as linear regression, decision tree regression, random forest regression, and lasso model. Each model was trained on a subset of the dataset and evaluated using appropriate evaluation metrics such as mean squared error (MSE) and R-squared value. The purpose of these experiments was to compare the performance of different regression models and identify the most suitable model for our specific task. Accordingly, the Linear regression model was our best choice because it showed the least MSE.

-  Outlier Handling

To handle these outliers, we implemented a post-processing step where we replaced negatively predicted values with zeros. This approach allowed us to address the outliers and ensure that the predicted statistics remain within a valid range. By zeroing out the negative values, we mitigated the impact of outliers on the model's performance and ensured that the predicted player statistics align with the expectations of NBA player performance.

## User Interface Development

- Player Stats and Prediction

The main dashboard (Fig 3.) incorporated several features, including a player drop-down menu, general player statistics, and predictions for the upcoming season. The drop-down menu allows users to select a specific player of interest. The general statistics displayed on the dashboard for the selected player provides an overview of their performance. These statistics include three-point percentage, two-point percentage, field goal percentage and other relevant metrics. Utilizing the selected player's past performance and the predictive model developed, the dashboard showcased point predictions for the player's performance in the upcoming season.

Fig 3. Dashboard showing selected player's predicted point for the upcoming season and other relevant pervious stats.

<img width="500" alt="image" src="https://github.com/Jayplect/credit-risk-classification/assets/107348074/075181c7-0604-4bc9-add1-df29c2d5762f">

- Leader board

The second tab- the leaderboard (Fig 4.), showed ranking for players based on average points, average assists, average three points percentage and average two point percentage for the past two seasons.

Fig 4. Leaderboard shwoing Rankings

<img width="500" alt="image" src="https://github.com/Jayplect/credit-risk-classification/assets/107348074/910e2054-0bc8-43e0-af8b-2df9a75a8d3f">

- Player Comparison

We also include a third tab to show player comparison based on selected position. The stats comparison are averages of the two previous seasons while the age and best ranks are the most recent details.

Fig 5. Player comparison based on selected position.

<img width="500" alt="image" src="https://github.com/Jayplect/credit-risk-classification/assets/107348074/3ed87912-c145-4e27-9a9c-d5a67a9bec83">

## Challenges Faced
During the course of the project, we encountered several challenges:
- Bad Encoding: The original data had encoding issues that we struggled to handle. We had to apply encoding techniques to ensure proper handling and interpretation of the data.
- External Factors: While player statistics provide valuable insights, it's important to note that other factors can influence a player's performance on the court. Factors such as injuries, team dynamics, coaching strategies, and external circumstances were not included in our analysis. Considering these external factors could further enhance the accuracy and predictive power of the model.

## Results
The prediction system adopted for this project achieved an impressive R-squared value of 0.9998, indicating a high level of accuracy in predicting player statistics based on the previous two seasons.
However, it is essential to note that player performance can be influenced by various external factors that were not considered in this analysis. Factors such as injuries, team dynamics, coaching strategies, and external circumstances can significantly impact a player's performance on the court. Therefore, it is important to interpret the predicted player statistics with caution and consider the broader context in which the players operate.
