# Evaluation Plan

## Goal

We want to make 2 week forecasts that beat the baseline model which we chose to be the Seasonal Average Model.

## Approach

1. Train on 2020-01-01 to 2025-02-28 data and use walk-forward validation.

2. Use test size of 14 days and use 26 folds to cover 364 days.

3. Using the walk-forward validation means that we would need to fit the model 26 times on each run. We should (within reason) try to always pick the "best" parameters that we can at that point in time.

4. Track the RMSE and MAPE of each fold. Take the average across the 26 folds as our metric to evaluate the model's performance. If there is a tie or the difference between RMSE is very close, we use the average MAPE as a tie breaker.

5. There is a chance that model performances are not optimal due to unoptimal choices in parameters. Upon picking a like best model, consider models which build on it e.g. Prophet -> NeuralProphet, Prophet + XGBoost. Tune parameters and check again.

6. Pick the model that has the best average RMSE after tuning.

7. Evaluate the model using walk-forward validation on the rest of the holdout data. If the model performs better than the baseline, then we are happy. If not, something has gone wrong and our model is either overfitting or underfitting. Try again.
