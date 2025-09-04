## Goal

Competition link:
https://www.kaggle.com/competitions/playground-series-s4e5/overview

- The goal of this competition is to predict the probability of a region flooding based on various factors.

- The dataset provided for this competition includes various features related to flooding, such as urbanization, deforestation, climate change and others.

- The target variable for this competition is flood probability.

## Dataset

| Feature                         | Definition |
|---------------------------------|------------|
| MonsoonIntensity                | Measure of rainfall strength and duration during the monsoon season. |
| TopographyDrainage              | Natural slope and terrain features affecting water runoff and drainage. |
| RiverManagement                 | Effectiveness of managing river flow, embankments, and channels. |
| Deforestation                   | Extent of forest loss reducing natural water absorption and flood control. |
| Urbanization                    | Expansion of cities and impervious surfaces increasing runoff. |
| ClimateChange                   | Long-term shifts in weather patterns influencing rainfall and floods. |
| DamsQuality                     | Structural integrity and maintenance of dams preventing uncontrolled water release. |
| Siltation                       | Accumulation of sediments in rivers and reservoirs reducing water capacity. |
| AgriculturalPractices           | Farming methods that may affect soil retention and water absorption. |
| Encroachments                   | Human settlements or construction in floodplains and riverbanks. |
| IneffectiveDisasterPreparedness | Lack of timely response, infrastructure, and planning for flood events. |
| DrainageSystems                 | Efficiency of artificial drainage infrastructure in handling heavy rains. |
| CoastalVulnerability            | Susceptibility of coastal regions to flooding from sea-level rise and storms. |
| Landslides                      | Slope failures that can block rivers or worsen flooding downstream. |
| Watersheds                      | Health and management of watershed areas affecting water flow regulation. |
| DeterioratingInfrastructure     | Aging roads, bridges, and levees that fail to withstand flood pressures. |
| PopulationScore                  | Density and distribution of people in flood-prone areas. |
| WetlandLoss                     | Reduction of wetlands that naturally absorb and store excess water. |
| InadequatePlanning              | Poor land-use planning and zoning contributing to flood risks. |
| PoliticalFactors                | Governance and policy issues affecting flood management decisions. |
| FloodProbability                | Likelihood of a flood event occurring under given conditions. |

## Evaluation

Submissions are based scored on the **$R^2$**.

Here is an example:

```
model = LinearRegression()

model.fit(X_train, y_train)

y_pred = model.predict(X_test)

score(y_test, y_pred)
```

## Instructions

There are three files provided: **Dataset**, **Test** and **Sample Submission** File

1. Use the **Dataset file** to train your model. Split this into train and test to calculate the **$R^2$**.
2. Do not use the **Test file** to train the model.
3. Once you have calculated the **$R^2$**., test the model using the **Test file** to generate your results
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
    'FloodProbability': y_pred
})

# Save the submission DataFrame to a CSV file
submission_df.to_csv('submission_file.csv', index=False)
print("Submission file created: submission_file.csv")
```

For each id row in the test set, you must predict the value of the target, FloodProbability. The file should contain a header and have the following format:

```
id,FloodProbability
1117957,0.5
1117958,0.5
1117959,0.5
...

```

# Linear Regression Model Grading Rubric

| Criterion            | Excellent (Full Marks) | Good (Partial Marks) | Poor (Low/No Marks) |
|----------------------|-------------------------|----------------------|---------------------|
| **Model Specification (30%)** | Correct predictors chosen, regression is appropriate, strong justification for model choice. | Reasonable predictors chosen, but justification weak or includes some irrelevant predictors. | Wrong model choice or predictors with no justification. |
| **Model Fit (40%)** | Uses R², Adjusted R², RMSE/MAE; interprets metrics correctly; clear discussion of goodness of fit. | Provides metrics but limited interpretation or missing key ones. | Metrics missing, incorrect, or misinterpreted. |
| **Visualization (30%)** | Includes residual plots, fitted vs. actual plots, or other diagnostics; interprets them clearly. | Provides some plots but with incomplete or weak interpretation. | No plots included or plots are used incorrectly. |

