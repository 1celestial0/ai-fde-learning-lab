# Learning Session Record — ML Foundations to R²

**Date:** 2026-08-07  
**Context:** AI Commando / FDE learning  
**Method:** course audio capture → concept correction → handwritten Python reasoning → notebook migration

This file preserves the important learning progression so the conversation does not disappear into chat history.

---

## 1. Course capture workflow established

The course is being consumed in chunks. The default workflow is:

1. Listen to the course.
2. Send a transcription chunk.
3. Capture it without interrupting with a long explanation.
4. Continue until a useful stopping point.
5. Switch into deep-learning mode when requested.
6. Rebuild the topic from first principles.

This avoids losing course context while also preventing every two-minute chunk from becoming a long detour.

---

## 2. ML foundation map learned

```text
Machine Learning
│
├── Supervised Learning
│   ├── Regression
│   └── Classification
│
├── Unsupervised Learning
└── Reinforcement Learning
```

Current path:

**ML → Supervised Learning → Regression → Simple Linear Regression → Multiple Linear Regression → Evaluation**

### Regression vs classification
- Regression → predict a continuous number: **How much?**
- Classification → predict a class/category: **Which class?**

---

## 3. Numerical vs categorical data

### Numerical
Arithmetic has useful meaning.
- age
- height
- revenue
- rainfall

Can be continuous or discrete.

### Categorical
Represents labels/groups.
- state
- color
- product category
- breed

Can be nominal or ordinal.

### Key correction
A value containing digits is not automatically numerical. A ZIP code can be categorical because adding or averaging ZIP codes does not represent a useful quantity.

---

## 4. X and Y mental model

Course language used independent/dependent variables.

More useful ML language:

- `X` = feature / input / predictor
- `Y` = target / output / response

Example:

`Rainfall → Crop Yield`

Important correction: calling rainfall an independent variable does **not** mean nothing else can influence rainfall. Also, regression association is not automatically proof of causation.

---

## 5. Simple linear regression core

Model:

```text
Ŷ = mX + c
```

- `m` = slope
- `c` = intercept
- `Ŷ` = predicted Y

Mental model:

> Find the line whose parameters create the smallest useful prediction error.

---

## 6. Tiny dataset used throughout

```python
x = [1, 2, 3, 4, 5]
y = [2, 4, 5, 4, 5]
```

### Important Python lesson from the handwritten exercise

Initial instinct used nested loops. That would pair every X with every Y and create 25 combinations.

Correct idea:

```python
for i in range(len(x)):
    print(x[i], y[i])
```

`x[i]` and `y[i]` belong to the **same training observation**.

---

## 7. Manual mean using loops

Instead of immediately using `sum()` or NumPy, totals were accumulated manually:

```python
x_total = 0
y_total = 0

for i in range(len(x)):
    x_total = x_total + x[i]
    y_total = y_total + y[i]

x_mean = x_total / len(x)
y_mean = y_total / len(y)
```

Results:

```text
x_mean = 3
y_mean = 4
```

This connected sigma notation with programming accumulation and SQL aggregation.

---

## 8. Deviations from the mean

For each row:

```text
x_diff = x[i] - x_mean
y_diff = y[i] - y_mean
```

| X | Y | X diff | Y diff |
|---:|---:|---:|---:|
|1|2|-2|-2|
|2|4|-1|0|
|3|5|0|1|
|4|4|1|0|
|5|5|2|1|

This became the bridge to the slope formula.

---

## 9. Slope understood as accumulated row-level arithmetic

Centered form:

```text
m = Σ[(x - x_mean)(y - y_mean)] / Σ[(x - x_mean)^2]
```

The key realization was that this is **not** a mysterious large formula and not a row-by-row division.

For each row:

```text
calculate x_diff
calculate y_diff
calculate x_diff * y_diff
calculate x_diff^2
accumulate both totals
```

Then divide once:

| Xdiff | Ydiff | Xdiff×Ydiff | Xdiff² |
|---:|---:|---:|---:|
|-2|-2|4|4|
|-1|0|0|1|
|0|1|0|0|
|1|0|0|1|
|2|1|2|4|
| | |6|10|

Therefore:

```text
m = 6 / 10 = 0.6
```

### Important course arithmetic correction

For this dataset:

```text
ΣX² = 55
ΣY² = 86
```

The course narration/transcription mixed those values at one point.

---

## 10. Intercept and final equation

```text
c = y_mean - (m * x_mean)
```

```text
c = 4 - (0.6 * 3)
c = 2.2
```

Final model:

```text
Ŷ = 0.6X + 2.2
```

The regression line passes through `(x_mean, y_mean)` for ordinary least squares with an intercept.

---

## 11. Prediction and residual

Prediction:

```text
Ŷ = mX + c
```

For `X = 1`:

```text
Ŷ = 0.6(1) + 2.2 = 2.8
```

Actual Y = 2.

Residual:

```text
Y - Ŷ = 2 - 2.8 = -0.8
```

Mental model:

> Residual = the model asking “How wrong was I on this observation?”

---

## 12. Why errors are squared

Simply adding residuals can produce zero because positive and negative errors cancel.

So least squares uses:

```text
SSE = Σ(Y - Ŷ)^2
```

For the dataset:

```text
SSE = 2.4
MSE = 0.48
RMSE ≈ 0.693
```

Also introduced:

```text
MAE = mean absolute error
```

---

## 13. Core ML learning loop recognized

```text
Input data
   ↓
Model
   ↓
Prediction
   ↓
Compare prediction with reality
   ↓
Loss / error
   ↓
Learn parameters that reduce error
```

This was identified as a reusable mental pattern that will later connect to larger ML and deep-learning models.

`model.fit(X, y)` should mentally mean:

> Learn model parameters from training data according to an objective/loss.

---

## 14. Multiple linear regression introduced

Simple:

```text
Ŷ = mX + c
```

Multiple:

```text
Ŷ = b0 + b1X1 + b2X2 + ... + bpXp
```

Course company example used:
- R&D Spend
- Administration
- Marketing Spend
- State
→ Profit

The key idea is not a new universe of mathematics: it is the linear-model idea expanded to several features.

---

## 15. Python ML toolchain introduced

Course introduced:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

### Correction
`sns` is **Seaborn**, not Pandas.

Pandas was used to:
- load CSV
- create a DataFrame
- inspect with `.head()`
- select columns/rows

---

## 16. Correlation heatmap

Course used a correlation visualization to compare numerical variables with profit.

Important interpretation:
- correlation measures association, not causation
- a heatmap is exploratory
- high predictor-to-predictor correlation can create multicollinearity
- categorical variables require appropriate encoding

---

## 17. Categorical encoding

The course used older `LabelEncoder` + old `OneHotEncoder(categorical_features=...)` syntax.

That API is outdated.

Modern practice should use `OneHotEncoder` via a `ColumnTransformer` or another current preprocessing pipeline.

Why encode?

A linear model cannot directly use text labels like:

```text
New York
California
Florida
```

Why not only map them to 0/1/2?

Because that can accidentally imply an artificial order/distance for a nominal category.

---

## 18. Dummy-variable trap

If all k one-hot columns are included along with an intercept, one can be reconstructed from the others.

Dropping one reference category is a common way to avoid perfect multicollinearity and improve interpretability.

---

## 19. Train/test split

Course used approximately:

```python
train_test_split(X, y, test_size=0.2, random_state=0)
```

Meaning:
- 80% training
- 20% testing
- `random_state=0` makes the split reproducible

Training data teaches the parameters.

Testing data asks whether the learned relationship works on unseen rows.

This introduced the concept of **generalization**.

---

## 20. `fit()`, `predict()`, coefficients and intercept

Training:

```python
regressor = LinearRegression()
regressor.fit(X_train, y_train)
```

Prediction:

```python
y_pred = regressor.predict(X_test)
```

Correct scikit-learn parameter attributes:

```python
regressor.coef_
regressor.intercept_
```

---

## 21. R² evaluation

Course used:

```python
r2_score(y_test, y_pred)
```

Mental model:

```text
R² = 1 - model_squared_error / mean_baseline_squared_variation
```

Important correction:

```text
R² = 0.93  ≠  “93% correct”
```

There is no universal requirement that R² must always be in the 0.90s.

A high R² must still be checked alongside:
- MAE/MSE/RMSE
- residual patterns
- leakage
- subgroup performance
- business consequences

---

## 22. Learning style decisions made

### Keep theory and code together
The preferred learning artifact is a living `.ipynb` notebook containing:
- theory
- intuition
- arithmetic
- code
- visualization
- interpretation
- data-engineering analogy
- pharma application
- PlantMind application
- exercises

### From-scratch before library
Use basic Python while a concept is new, then show the professional library version.

### Rebuild instead of copy-paste
Working code is not considered mastery until it can be reconstructed and explained.

### Break working systems
PlantMind 2.0 will be used as a reverse-engineer → understand → rebuild learning track.

---

## 23. Development environment decided

```text
GitHub = source of truth / memory
VS Code = local development workspace
Google Colab = browser/cloud notebook runtime
ChatGPT = learning architect / tutor / repo maintainer
```

GitHub will preserve version history and allow the same `.ipynb` notebook to be opened from multiple devices.

---

## 24. Safety boundary

This is a **public learning repository**.

Do not commit:
- LTTS proprietary information
- Jazz/client datasets
- credentials/API keys
- internal documents
- confidential code

Use public, synthetic, or personally owned material only.

---

## 25. Next learning node

Immediate sequence:

```text
finish Simple Linear Regression hands-on
        ↓
Multiple Linear Regression practice
        ↓
Model evaluation / R² / MAE / RMSE
        ↓
continue AI Commando ML curriculum
```

The detailed executable lessons live in the `notebooks/` directory. This session record exists so the **reasoning journey itself is not lost**.
