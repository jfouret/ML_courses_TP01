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

**TODO #1**: Import the dataset using panda

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

## 2. Data

### 2.1 The target

- Which column would be the target ?

<details><summary>Answer</summary>
charges
</details>

### 2.2 The features

- Which features are discrete ?

<details><summary>Answer</summary>
children, smoker, region
</details>

- Which features are Finite ?

<details><summary>Answer</summary>
age, dmi, children, charges
</details>

- Which features are Bounded ?

<details><summary>Answer</summary>
age, sex, children, smoker
</details>

### 2.3 Dummy model with all variable

- Write the model equation

- Try to find the parematers using the best available method


