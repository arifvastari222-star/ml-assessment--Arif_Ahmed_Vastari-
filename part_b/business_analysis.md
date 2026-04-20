# Part B: Business Case

## B1. Problem Formulation
### B1 (a) Problem Formulation

- Target variable: items_sold (number of items sold)

- Input features:
  promotion type, store size, location type, competition density, customer behavior, time (month, weekend, festival)

- Type of problem: Regression

- Reason:
  Because we are predicting a numeric value (items sold), so it is a regression problem

  ### B1 (a) Problem Formulation

- Target variable: items_sold (number of items sold)

- Input features:
  promotion type, store size, location type, competition density, customer behavior, time (month, weekend, festival)

- Type of problem: Regression

- Reason:
  Because we are predicting a numeric value (items sold), so it is a regression problem

  ### B1 (c)

- Instead of one global model, we can create different models for different store types or locations

- Example:
  separate model for urban, semi-urban and rural stores

- This is better because customer behavior is different in each location

## B2. Data and EDA Strategy
### B2 (a)

- We will join all tables using common keys like store_id and date

- Final dataset:
  one row = one store per day (or per transaction)

- We may aggregate data like:
  total items sold per day per store
  total visits or sales per day

- This helps in simplifying the dataset for modeling

### B2 (a)

- We will join all tables using common keys like store_id and date

- Final dataset:
  one row = one store per day (or per transaction)

- We may aggregate data like:
  total items sold per day per store
  total visits or sales per day

- This helps in simplifying the dataset for modeling

### B2 (c)

- Since 80% data has no promotion, model may become biased towards no-promotion cases

- To fix this:
  we can balance the data or give importance to promotion cases

- This helps model learn better about promotion impact

## B3. Model Evaluation and Deployment

### B3 (a)

- Use time-based split (train on past, test on future)

- Random split is not correct because it mixes past and future data

- Metrics:
  RMSE → shows error size
  MAE → shows average error

- Lower values mean better model

### B3 (b)

- Feature importance helps understand why model gives different results

- For example:
  in December, festivals or holidays may increase sales
  in March, normal demand may be lower

- We can explain that different features have different impact in different months

### B3 (c)

- Save model using pickle or joblib

- Every month:
  new data is prepared in same format
  model is used to predict best promotion

- Monitor model performance over time

- If performance drops, retrain the model with new data