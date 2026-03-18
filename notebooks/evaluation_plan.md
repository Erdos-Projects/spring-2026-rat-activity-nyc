# Evaluation Plan

0. We have data from 2020-01-01 to 2026-02-28. Holdout 2025-03-01 to 2026-02-28.

1. Each model gets trained on data for the dates 2020-01-01 to 2025-02-28.

2. Use walk-forward cross-validation with 26 folds and 14 day test sizes to prevent overfitting.

3. Compute RMSEs for each fold. Metric used is the mean RMSE over the 26 folds.

4. Reasonably tune parameters and continue to use walk-forward cross-validation to prevent overfitting and mean RMSE to determine performance of model.

5. Select the best performing model while balancing runtime.

6. After choosing the best performing model with its tuned parameters, evaluate its performance on holdout set. Take the mean RMSE. For it to be a good model, it should perform noticeably better or within the same rage as it was performing on before while also being better than the baseline model.