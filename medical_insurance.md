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

### **TODO 1.1**: Import the dataset using panda

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

### Features and targets

- Which column would be the target ?

<details><summary>Answer</summary>
charges
</details>

- Which features are Discrete ?

<details><summary>Answer</summary>
children, smoker, region
</details>

- Which features are Finite ?

<details><summary>Answer</summary>
age, bmi, children, charges
</details>

- Which features are Bounded ?

<details><summary>Answer</summary>
age, sex, children, smoker
</details>

### **TODO 1.2** Simple Linear Model

- Write the model equation

- Setup the matrix X and Y while encoding the discrete values

<details><summary>Hints</summary>
use `get_dummies` method to transform discrete values. Use wisely the argument `drop_first`.
</details>

<details><summary>Hints</summary>
Do not forget the intercept. You might use `np.insert` function.
</details>

- Encoding the discrete values for a linear model

- Formulate and solve the optimization problem using linear algebra

<details><summary>Bonus</summary>
`scipy.linalg.det` is useful to ensure there is a analytical solution.
</details>

<details><summary>Hints</summary>
`@` is the operator for matrix multiplication. `scipy.linalg.inv` is useful .
</details>

- Calculate the predicted values

### **TODO 1.3** Diagnostics

- What does the residuals look like ?

<details><summary>Hints</summary>
`seaborn.histplot` is usefull.
</details>

- What do you think of the residuals ?

- How well the model perform ? **How can we evaluate the model ?**

<details><summary>Hints</summary>
`seaborn.histplot` is usefull.
</details>

### **TODO 1.4**

- Can you create a new pertinent feature from your observatios ?

<details><summary>Hints</summary>
With a BMI above 30, ont fall into obesity.
</details>
