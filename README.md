# Predicting NHL MVP with Random Forest

The Hart Memorial Trophy is awarded at the end of each NHL season to the league's most valuable player. Several factors influence decision, but none more so than individual player performance. This model aims to use individual statistics to predict whether a player has had an MVP-caliber season or not.

## Data

Player statistics were gathered from MVP candidates of the last 45 NHL seasons. Any player to recieve a single vote was considered in the dataset. The choice to only consider data from after 1980 is supposed to reflect modern changes to the game, like season length, voting procedures, and scoring frequency.

## 2-Model Approach

In order to reconcile the disparate statistics used to evaluate goalie and skater performance, two models are employed. One handles skater data and the other goalie data. Due to high class imbalance, both models were trained on oversampled data; SMOTE was used in the skater model, and RandomOverSampler in the goalie model. Also, each model was optimized for F1-score, as neither precision nor recall stands out as overtly more significant than the other in this scenario.

## Predicting 2025 MVP

After compiling statistics for the current season's best skaters and goalies, forecasting was done to create a dataset that the models could work with. Comparisons between the models can be made by taking the proportion of trees in the random forest that predicted a player to win MVP. The player with the highest proportion across both models, based on forecasted data from December 12th, 2024, was Leon Draisaitl of the Edmonton Oilers.

## Model Limitations and Error

Individual statistics may be the most important metric used by voters to select an MVP, but there are others. Team success and media discourse play a role in determining MVP, but they are not considered by this model. Similarly, the relatively small and highly imbalanced nature of the dataset makes classification and prediction a difficult task. A more advanced model/sampling methods may be required.
