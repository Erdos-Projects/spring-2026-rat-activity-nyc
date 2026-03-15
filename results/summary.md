<<<<<<< Updated upstream
=======
# Summary of Results

## Citywide

## Manhattan

The best performing model we found was the Prophet model. For our walk-forward cross validation with 26 folds and 14 day forecast horizons, Prophet got an average RMSE of 4.58 beating out the second place contender of SARIMA which got an average RMSE of 4.98.

<p align="center">
  <img src="modeling/manhattan_comparisons.png" width="1500" alt="Logo" />
</p>

<p align="center">
  <img src="modeling/manhattan_comparisons_plot.png" width="1500" alt="Logo" />
</p>

Next, we considered potential upgrades to Prophet. We tried both NeuralProphet and a Hybrid model using Prophet together with XGBoost. Our results (displayed below; left is NeuralProphet and right is the Hybrid Model) showed that NeuralProphet performed slightly better than Prophet, but not enough to justify the increased runtime for NeuralProphet. We used NeuralProphet's n_lags parameter and added regressors to it. Our choices were to use 'apparent_temperature_max', 'apparent_temperature_min', and 'snowfall_sum' obtained from Open-Meteo. Our work in the folder scr/features suggested that these features could be used to improve our model. As for the hybrid model, we many features for the XGBoost model on residuals.  We know from our work at the citywide level that the residuals exhibit a lot of noise and to account for that, we included a lot of features. We used Optuna's hyerparameter for this purpose. The results of one run is displayed to the right. We see that it actually performed worse in that run. We do have reasons to believe that we can improve on Prophet by tuning hyparameters some more. This is quite computationally intensive and have not made extended attempts to do that.

<p align="center">
  <img src="modeling/manhattan_neural_prophet.png" width="175" alt="Logo" />
  &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; 
    <img src="modeling/manhattan_hybrid.png" height="575" alt="Logo" />
</p>



## Brooklyn

## Staten Island

## Bronx

## Queens

## Weekly Forecasting
>>>>>>> Stashed changes
