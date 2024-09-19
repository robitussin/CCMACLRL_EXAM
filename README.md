## Goal

- The goal of this competition is to predict the price of used cars based on various attributes.

- The dataset provided for this competition includes various features related to used cars, such as the car's model, year of manufacture, mileage, fuel type, transmission type, and engine power.

- The target variable for this competition is the price of the used car.

## Dataset

| Variable Name | Definition                                                |
| ------------- | --------------------------------------------------------- |
| id            | Unique identifier for each entry                          |
| brand         | Brand of the vehicle                                      |
| model         | Model of the vehicle                                      |
| model_year    | Year the vehicle model was manufactured                   |
| milage        | Mileage of the vehicle (in miles)                         |
| fuel_type     | Type of fuel the vehicle uses (e.g., Gasoline, Flex Fuel) |
| engine        | Engine specification including horsepower and type        |
| transmission  | Type of transmission (e.g., A/T, Dual Shift Mode)         |
| ext_col       | Exterior color of the vehicle                             |
| int_col       | Interior color of the vehicle                             |
| accident      | Information about any accidents or damages reported       |
| clean_title   | Indicates if the vehicle has a clean title (Yes/No)       |
| price         | Price of the vehicle                                      |

## Evaluation

Submissions are based scored on the **Root Mean Squared Error (RMSE)**.

To get the root mean squared error, use `mean_squared_error()` and set `squared=False`

Here is an example:

```
model = LinearRegression()

model.fit(X_train, y_train)

y_pred = model.predict(X_test)

mean_squared_error(y_test, y_pred, squared=False)
```

## Instructions

There are three files provided: **Dataset**, **Test** and **Sample Submission** File

1. Use the **Dataset file** to train your model. Split this into train and test to calculate the **RMSE**
2. Do not use the **Test file** to train the model.
3. Once you have calculated the **RMSE**, test the model using the **Test file** to generate your results
4. The generated format should be similar to the **Sample Submission** File
5. Upload your **python notebook** and your **submission file** to your **CCMACLRL_EXAM** repository in GitHub
6. Submit your results to **kaggle**.

Here is a sample on how to create a **Sample Submission** File

```
id = sf.pop('id')
y_pred = model.predict(dt)

# Create a submission DataFrame
submission_df = pd.DataFrame({
    'id': id,
    'class': y_pred
})

# Save the submission DataFrame to a CSV file
submission_df.to_csv('submission_file.csv', index=False)
print("Submission file created: submission_file.csv")
```

For each id in the test set, you must predict the price of the car. The file should contain a header and have the following format:

```
id,price
188533,43878.016
188534,43878.016
188535,43878.016
...

```
