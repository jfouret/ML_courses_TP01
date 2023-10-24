# Predict medical insurance costs

In the Practical session we will se how to use whant we have learn about models to best predict the insurance costs.

## 1. Dataset

The datasets comes from Kaggle: https://www.kaggle.com/datasets/joebeachcapital/medical-insurance-costs/

The licence is open.

Columns: 
- `age`
- `sex`
- `bmi`
- `children`
- `smoker`
- `region`
- `charges`

Download the dataset from kaggle and add it into the notebook environment.

### 1.1 Import the dataset using pandas

- Import the datasets
<details><summary>Hints</summary>
use `pandas.read_csv`
</details>

- Print the nature of each column
<details><summary>Hints</summary>
use `dtypes attribute`
</details>

- Show a summary of each column

- What is the size of the data

<details><summary>Hints</summary>
use `shape` attribute
</details>

### 1.2 Features and Targets

- Which column would be the target ?

<details><summary>Answer</summary>
charges
</details>

- Which features are Discrete ?

<details><summary>Answer</summary>
age, bmi, children, charges
</details>

- use dataviz to understand relations features-variables

<details><summary>Hints</summary>
use `pd.melt` and `sns.relplot`
</details>

## 2. Simple Linear Model

### 2.1 Simple Linear Model: Setup

- Write the model equation

- Setup the matrix X and Y while encoding the discrete values

<details><summary>Hints</summary>
use `get_dummies` method to transform discrete values. Use wisely the argument `drop_first`.
</details>

<details><summary>Hints</summary>
Do not forget the intercept. You might use `np.insert` function.
</details>

- Encoding the discrete values for a linear model

### 2.2 Simple Linear Model: Solving and Prediction

- Formulate and solve the optimization problem using linear algebra

<details><summary>Bonus</summary>
`scipy.linalg.det` is useful to ensure there is a analytical solution.
</details>

<details><summary>Hints</summary>
`@` is the operator for matrix multiplication. `scipy.linalg.inv` is useful .
</details>

- Calculate the predicted values

### 2.3 Simple Linear Model: **Diagnostics**

- What does the residuals look like ?

<details><summary>Hints</summary>
`seaborn.histplot` is usefull.
</details>

- What do you think of the residuals ?

- How well does the model perform ? **How can we evaluate the model ?**

<details><summary>Hints</summary>
`seaborn.histplot` is usefull.
</details>

- Use dataviz to check features with residuals

## 3. New feature and interaction term

### 3.1 Adding a feature

- Can you create a new pertinent feature from your observatios ?

<details><summary>Hints</summary>
With a BMI above 30, one fall into obesity.
</details>

### 3.2 Solving a linear model with an interaction between 2 features

- Solve the optimization problem and find the best parameters
- Check residuals
- Use dataviz to check features with residuals

## 4. statmodels packages

### 4.1 OLS with Formula API

```
results1 = smf.ols('charges ~ age + sex + bmi +  children + smoker + region + obesity', data=df2).fit()
results1.summary()
```
### 4.2 Model selection

- add a model with the interaction term `+ obesity:smoker`
- Compare models with AIC, BIC and LRT test

## 5. In-sample and out-sample errors

### 5.1 North vs South

- Split the dataset between south and north based on region.
- Train a model with south data
- Compare its performance using sum of squared error and R2 between the 2 datasets.
- What is the difference ? Comment.

### 5.2 Sample 1 vs Sample 2

- Do the same with 2 sample of the data frame
- start with 2 sample of 100
- try, 20 and 50
- Each time look at the sum of squared errors and r2
- Comment

## 6. Full ML workflow

- Introduction of the terms
- training dataset
- validation dataset
- test dataset
- adversarial dataset
