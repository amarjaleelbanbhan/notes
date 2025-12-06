# COMPLETE EXAM PREPARATION GUIDE
## Data Science & Machine Learning

---

# 1. COMPLETE TOPIC MAP

## 1.1 DATA FUNDAMENTALS

### Structured Data
- **Elements**: Data comes from sensors, events, text, images (unstructured → must be structured)
- **Rectangular Data Format** (Data Frames)
  - Rows = Records/observations
  - Columns = Features/variables/attributes
  - Used in spreadsheets, databases (SQL), Python (pandas), R
  
### Data Types

#### Numeric Data
- **Continuous**: Any value in range (wind speed, time)
- **Discrete**: Specific integers (clicks, counts)

#### Categorical Data
- **Nominal**: Categories without order (TV types: LCD, LED)
- **Binary**: Two values (yes/no, true/false)
- **Ordinal**: Ordered categories (ratings: 1-5 stars)

### Nonrectangular Structures
- Time series data
- Spatial data
- Requires specialized algorithms & visualization

---

## 1.2 EXPLORATORY DATA ANALYSIS (EDA)

### Estimates of Location (Central Tendency)

#### Mean (Average)
- Sum of all values / count
- Simple but **sensitive to outliers**

#### Trimmed Mean
- Removes extreme values (e.g., top/bottom 10%)
- Reduces outlier influence
- Compromise between mean and median

#### Weighted Mean
- Some values more important/reliable than others
- Used for: unequal sensor accuracy, underrepresented groups

#### Median
- Middle value when sorted
- **Robust** measure (resistant to outliers)
- Better for skewed data

### Estimates of Variability (Dispersion)

#### Variance & Standard Deviation
- Measure spread around center
- Formula: SD = √(Σ(x - mean)² / n)
- **Sensitive to outliers**

#### Mean Absolute Deviation (MAD)
- Average absolute distance from mean
- More robust than SD

#### Percentiles & Quartiles
- **Percentile**: Value below which P% of data lies
- **Quartile**: 25%, 50% (median), 75%
- **IQR** (Interquartile Range) = Q3 - Q1

#### Median Absolute Deviation (MAD from median)
- Most robust variability measure

### Distribution Visualization

| **Visualization** | **Purpose** | **Best For** |
|---|---|---|
| **Histogram** | Shows frequency distribution | Continuous data, spotting skewness |
| **Box Plot** | Shows median, quartiles, outliers | Comparing distributions across groups |
| **Density Plot** | Smooth estimate of probability density | Identifying peaks, gaps, multiple modes |
| **Percentile/Quantile** | Shows spread of data | Understanding tail behavior |

### Correlation Analysis

#### Pearson's r (Linear Correlation)
- Range: -1 to +1
- +1 = Perfect positive correlation
- -1 = Perfect negative correlation
- 0 = No linear correlation
- **Measures only linear relationships**

#### Correlation Matrix
- Shows pairwise correlations between multiple variables

#### Types of Correlation
- **Positive**: One variable increases → other increases
- **Negative**: One variable increases → other decreases

### Visualization for Relationships

| **Data Type Combo** | **Best Visualization** |
|---|---|
| Numeric vs Numeric | Scatterplot, Hexbin, Contour |
| Categorical vs Categorical | Contingency Table |
| Numeric vs Categorical | Boxplot, Violin Plot |
| Multiple Variables | Pair plots, PCA, 3D plots |

### Univariate, Bivariate, Multivariate Analysis

- **Univariate**: 1 variable (mean, variance, histogram)
- **Bivariate**: 2 variables (correlation, scatterplot)
- **Multivariate**: 3+ variables (advanced plots, PCA)

---

## 1.3 SAMPLING & DISTRIBUTIONS

### Sampling Concepts

#### Random Sampling
- Each element selected by random mechanism
- Can be with or without replacement
- **Goal**: Unbiased sample

#### Bias
- Sample doesn't represent population
- **Selection bias**: Data chosen in skewed way
- **Nonrandom sampling**: Non-random selection process
- **Large biased sample < small unbiased sample**

#### Selection Bias Examples
- Marketing analysis of active users only (ignores churned)
- Stopping experiment when results look "interesting"

#### Regression to Mean
- Extreme observations followed by more average ones
- Random variation balances over time
- **Example**: Great rookie year (skill + luck) → mediocre year (luck fades)

### Sampling Distribution

#### Definition
- Distribution of a statistic (sample mean, proportion) across repeated samples
- Shows how statistic varies from sample to sample

#### Properties
- **Center**: Mean of sampling distribution ≈ population mean
- **Spread**: Standard Error (SE)
- **Shape**: Often normal (bell-curve) for large samples

#### Standard Error (SE)
- Formula: SE = SD / √n
- Smaller SE = more precise estimate
- **Bigger sample → smaller SE**

### Central Limit Theorem (CLT)

#### Key Points
1. For large samples, sampling distribution ≈ normal
2. Works even if population is NOT normal
3. Mean of sampling distribution = population mean
4. SD of sampling distribution = population SD / √n

#### Importance
- Allows confidence intervals and hypothesis testing
- Justifies using normal distribution even for non-normal data

### Bootstrap (Resampling)

#### Process
1. Take original sample as "population"
2. Resample WITH replacement many times (e.g., 1000)
3. Compute statistic (mean, median) for each resample
4. Distribution of these statistics = bootstrap distribution

#### Advantages
- Works without assuming normal distribution
- Works for small samples
- Works for skewed data
- Can estimate SE and confidence intervals

#### Example
- Original sample: 10 values
- Create 1000 bootstrap samples (each n=10)
- Calculate mean for each
- 1000 bootstrap means ≈ sampling distribution of mean

### Confidence Intervals (CI)

#### Definition
- Range of values likely to contain true population parameter
- Example: "95% confident mean is between 78 and 85"

#### Interpretation
- If you repeat sampling 100 times, ~95 times the CI will contain true parameter
- **NOT** 95% chance true value is in THIS interval (already happened)

#### 95% CI Formula
- CI = Sample Mean ± (Critical Value × SE)
- For normal: Critical Value ≈ 1.96
- For t-distribution: Depends on degrees of freedom

#### 99% CI
- Wider than 95% (more confidence)
- Formula uses 2.58 instead of 1.96

### Probability Distributions

#### Normal Distribution
- Bell-shaped, symmetric
- Defined by: Mean (μ) and SD (σ)
- Mean = Median = Mode
- 68% within 1 SD, 95% within 2 SD

#### Student's t-Distribution
- Similar to normal but heavier tails
- Used when SD is estimated from sample
- More spread than normal (especially small samples)
- Approaches normal as n increases

#### Binomial Distribution
- Models success/failure in fixed trials
- Each trial has 2 outcomes only
- Parameters: n (trials), p (probability of success)
- Used for: pass/fail, buy/don't buy, click/don't click

#### Chi-Square Distribution
- Sum of squared independent normal variables
- Used for testing categorical data
- Always positive, right-skewed
- Degrees of freedom = number of categories - 1

#### F-Distribution
- Compares two variances
- Used to test if variability between groups > within groups
- Ratio of two chi-squares
- Always positive

#### Poisson Distribution
- Models count of events in fixed time/space
- Parameter: λ (average count)
- Used for: email arrivals, defects per batch, accidents per year
- Mean = Variance = λ

#### Long-Tailed Distribution
- Tails extend much farther than normal
- More extreme values than normal distribution
- Common in real-world data (income, web traffic)

---

## 1.4 MACHINE LEARNING FUNDAMENTALS

### What is Machine Learning?

#### Definition
- Subset of AI
- Algorithms learn patterns from training data
- Make predictions on new data
- **Without explicit hard-coded instructions**

#### Key Components
- **T** (Task): Classification, regression, clustering
- **E** (Experience): Training data
- **P** (Performance): How well model predicts

### Types of Machine Learning

#### Supervised Learning
- **Requires labeled data** (output known)
- Use cases: Risk assessment, fraud detection, image recognition
- Two main types:

##### Classification
- Predict **discrete categories** (classes)
- Output: Labels (Yes/No, Pass/Fail, Cat/Dog)
- Examples: Email spam/not spam, disease present/absent

###### Binary Classification
- 2 classes only
- Example: Phishing email (Yes/No)

###### Multi-class Classification
- 3+ classes
- Example: Animal type (Cat/Dog/Cow)

###### Multi-label Classification
- Single item = multiple labels
- Example: Movie = Action + Comedy

##### Regression
- Predict **continuous numbers**
- Output: Numeric values
- Examples: House price, temperature, stock price

#### Unsupervised Learning
- **No labeled data**
- Discover hidden patterns
- Main type: **Clustering** (group similar items)
- Uses: Market segmentation, anomaly detection

#### Semi-Supervised Learning
- **Mix of labeled + unlabeled data**
- Learns from both
- Used when labeling is expensive
- **Active Learning**: Model suggests which samples to label

#### Reinforcement Learning
- **Learn from interaction with environment**
- Agent receives rewards/penalties
- Goal: Maximize total reward
- Components: AI, animal psychology, control theory
- Uses: Game playing, robotics, autonomous driving

#### Self-Supervised Learning
- Creates labels automatically from data
- Example: Predicting next frame in video

### Common Supervised Learning Algorithms

| **Algorithm** | **Type** | **Use Case** | **Key Idea** |
|---|---|---|---|
| **Linear Regression** | Regression | Predict continuous values | Fit straight line through data |
| **Logistic Regression** | Classification | Binary classification | Map to probability (0-1) |
| **Decision Trees** | Both | Easy to understand | Ask series of yes/no questions |
| **SVM** | Classification | Separate classes | Find best dividing line/boundary |
| **Naïve Bayes** | Classification | Text/spam filtering | Use probability, assume feature independence |
| **Random Forest** | Both | High accuracy | Combine many decision trees |
| **K-NN** | Both | Pattern matching | Find k nearest neighbors, vote |

---

## 1.5 LINEAR REGRESSION (SIMPLE & MULTIPLE)

### Simple Linear Regression

#### Definition
- **One independent variable (X)** predicts **one dependent variable (Y)**
- Relationship: Y = mX + b
- Assumes **linear relationship**

#### Key Components

##### Slope (m)
- Change in Y per unit change in X
- Steeper slope = stronger relationship
- Formula: m = Σ(x - x̄)(y - ȳ) / Σ(x - x̄)²

##### Y-Intercept (b)
- Value of Y when X = 0
- Where line crosses Y-axis
- Formula: b = ȳ - m × x̄

##### Best Fit Line
- Minimizes **total squared distance** from points to line
- Points closest to line = better fit
- **Least Squares Method**: Minimize sum of squared errors

#### Error/Residual
- Difference between actual (Y) and predicted (Y')
- Residual = Y - Y'
- Goal: Minimize sum of squared residuals

#### Cost Function (Mean Squared Error)
- Formula: J = (1/2m) × Σ(hθ(x) - y)²
- m = number of data points
- hθ(x) = predicted value
- Smaller cost = better fit
- If cost = 0: Perfect fit

#### Optimization: Gradient Descent
1. Start with random slope & intercept
2. Calculate cost function
3. Adjust parameters in direction of decreasing cost
4. Repeat until convergence (cost stops decreasing)
5. Find minimum cost → best parameters

### Multiple Linear Regression

#### Definition
- **Multiple independent variables (X1, X2, ... Xp)** → **one Y**
- Equation: Y = b0 + b1X1 + b2X2 + ... + bpXp
- Extension of simple regression

#### When to Use
- Real data usually needs multiple features
- Better predictions than single variable
- Example: House price = size + rooms + location + age

#### Same Concepts Apply
- Still minimize squared errors
- Still use gradient descent
- Still have cost function
- Still calculate slope (coefficient) for each variable

### Model Evaluation

#### R-Squared (R²)
- Measures **proportion of variance explained**
- Range: 0 to 1
- 1 = perfect fit, 0 = poor fit
- Interpretation: "Model explains X% of variation in Y"

#### Root Mean Squared Error (RMSE)
- Square root of average squared errors
- Same units as Y
- Lower = better predictions
- Punishes large errors heavily

#### Mean Absolute Error (MAE)
- Average absolute error
- More interpretable than RMSE
- Doesn't punish large errors as heavily

### Prediction vs Explanation (Profiling)

#### Prediction
- **Goal**: Forecast future Y values
- **Focus**: Accuracy on new data
- **Methods**: ML models, complex algorithms
- **Evaluation**: RMSE, MAE, R²

#### Explanation (Profiling)
- **Goal**: Understand why relationship exists
- **Focus**: Interpretability and insight
- **Methods**: Statistical models, coefficients, p-values
- **Evaluation**: Significance tests, confidence intervals, effect size

---

## 1.6 CLASSIFICATION

### Definition
- Predict **discrete categories** (classes/labels)
- Different from regression (which predicts numbers)
- Goal: Assign new data to correct category

### Types of Classification Problems

| **Type** | **Classes** | **Example** |
|---|---|---|
| **Binary** | 2 | Spam/Not Spam, Pass/Fail |
| **Multi-class** | 3+ | Animal type, Disease type |
| **Multi-label** | Multiple per item | Movie: Action + Comedy |

---

## 1.7 LOGISTIC REGRESSION

### What & Why

#### Definition
- Supervised ML algorithm for **binary classification**
- Different from linear regression: predicts **probability** (0-1), not continuous values
- Output: Probability that X belongs to class 1
- **0.5 threshold**: P ≥ 0.5 → Class 1, P < 0.5 → Class 0

#### Why Not Linear Regression?
- Linear regression predicts any value (< 0 or > 1)
- We need output between 0 and 1 (probability)
- Logistic regression "squashes" output to [0, 1]

#### Real-World Examples
- Phishing detection: Email phishing (1) or not (0)
- Customer churn: Will leave (1) or stay (0)
- Ad click: User clicks (1) or not (0)
- Disease: Patient has disease (1) or not (0)

### Sigmoid Function

#### Definition
- "S-shaped" curve
- Formula: σ(z) = 1 / (1 + e^(-z))
- Transforms any value → probability [0, 1]

#### Properties
- As z → ∞, σ(z) → 1
- As z → -∞, σ(z) → 0
- At z = 0, σ(z) = 0.5

#### How It Works
1. Linear combination: z = θ0 + θ1×X1 + θ2×X2 + ...
2. Apply sigmoid: P = 1 / (1 + e^(-z))
3. Result: Probability between 0 and 1

### Decision Boundary

#### Definition
- Threshold separating class 0 from class 1
- Default: 0.5

#### Decision Rule
- If P(Y=1) ≥ 0.5 → Predict Class 1
- If P(Y=1) < 0.5 → Predict Class 0

#### Threshold Tuning
- Can adjust 0.5 threshold based on problem needs
- Lower threshold (e.g., 0.3) → More sensitive to Class 1
- Higher threshold (e.g., 0.7) → More conservative

### Cost Function (Log Loss / Cross-Entropy)

#### Formula
- J = -(1/m) × Σ[y×log(ŷ) + (1-y)×log(1-ŷ)]
- y = actual value (0 or 1)
- ŷ = predicted probability
- m = number of samples

#### Intuition
- Penalizes confident wrong predictions heavily
- If true = 1 but predicted = 0.1, loss is high
- If true = 0 but predicted = 0.9, loss is high

### Multi-class Logistic Regression

#### When Used
- 3+ classes to predict
- Example: Fruit type (Apple, Banana, Orange)

#### Difference from Binary
- Uses **Softmax function** instead of sigmoid
- Softmax converts multiple outputs to probabilities summing to 1
- Outputs probability for **each class**

---

## 1.8 NAÏVE BAYES

### Foundation: Bayes' Theorem

#### Formula
- P(y|X) = P(X|y) × P(y) / P(X)

#### Components
- **P(y|X)**: Posterior probability (what we want to find)
- **P(X|y)**: Likelihood (probability of data given class)
- **P(y)**: Prior probability (class frequency in training)
- **P(X)**: Evidence (total probability of data)

#### Interpretation
- What's probability of class y given features X?

### Naïve Assumption

#### Core Idea
- **All features are conditionally independent given the class**
- Feature 1 doesn't affect feature 2, given we know the class
- **Simplifies calculation drastically**

#### Why "Naïve"?
- Real features often correlated
- This assumption rarely true in reality
- BUT: Surprisingly effective in practice!

### How Naïve Bayes Works

#### Training Phase
1. Calculate **prior probability**: P(class) = count of class / total
2. For each feature & class, calculate **likelihood**:
   - P(feature_value | class) = count / total for that class
3. Build frequency/probability tables

#### Prediction Phase
1. For new sample with features X
2. Calculate P(y|X) for each possible class
3. Choose class with highest probability

#### Example: Golf Dataset
- Dataset: Weather conditions → Play Golf (Yes/No)
- Features: Outlook, Temperature, Humidity, Wind
- Training: Build tables of P(each weather value | Yes) and P(each weather value | No)
- Prediction: Given new conditions, calculate P(Yes | conditions) and P(No | conditions)

### Types of Naïve Bayes

| **Type** | **Data Type** | **Use Case** |
|---|---|---|
| **Gaussian NB** | Continuous | Assumes normal distribution for features |
| **Multinomial NB** | Discrete counts | Text classification (word counts) |
| **Bernoulli NB** | Binary (present/absent) | Text (word present or not) |

### Advantages & Use Cases
- Fast training and prediction
- Works well with high-dimensional data (text)
- Good for spam filtering, text categorization, sentiment analysis
- Needs small training data

---

## 1.9 K-NEAREST NEIGHBORS (KNN)

### Definition

#### Concept
- **Non-parametric** (no assumptions about data distribution)
- **Supervised** learning (uses labeled data)
- Works for **both classification and regression**

#### Core Principle
- **Similar points are near each other** in feature space
- To classify new point: Look at k nearest labeled neighbors
- For classification: Majority vote
- For regression: Average of k neighbors' values

#### Simplicity
- Easy to understand and implement
- No real "training" phase (lazy learner)
- Just remembers all training data

### K: Number of Neighbors

#### Choosing k

##### Small k (e.g., k=1, 3)
- **Pro**: Captures local patterns
- **Con**: Sensitive to noise/outliers → overfitting

##### Large k (e.g., k=100)
- **Pro**: More stable, reduces variance
- **Con**: Smooths out local patterns → underfitting
- **Con**: May consider neighbors very far away

#### Optimal k
- Usually determined by cross-validation
- Test different k values, pick best performance
- Common: k = 3, 5, 7 (odd numbers to avoid ties)

### Working Steps

#### Step 1: Choose k
- Decide number of neighbors to consider

#### Step 2: Calculate Distances
- Compute distance from new point to ALL training points
- Distance metrics: Euclidean, Manhattan, Minkowski

#### Step 3: Find k Nearest Neighbors
- Sort all distances, pick k smallest
- These k points are nearest neighbors

#### Step 4: Classify (or Regress)
- **Classification**: Majority vote (most common class among k neighbors)
- **Regression**: Average of k neighbors' values

### Distance Metrics

#### Euclidean Distance
- Formula: d = √[(x₁-x₂)² + (y₁-y₂)²]
- Straight-line distance
- Most common, sensitive to scale

#### Manhattan Distance
- Formula: d = |x₁-x₂| + |y₁-y₂|
- Sum of absolute differences
- Less sensitive to outliers

#### Minkowski Distance
- General formula: d = (Σ|xᵢ-yᵢ|^p)^(1/p)
- p=2 → Euclidean
- p=1 → Manhattan
- Used for other scenarios

### Data Preprocessing for KNN

#### One-Hot Encoding
- Convert categorical variables to numeric
- Each category → binary column (1 if present, 0 otherwise)
- Example: Color (Red, Blue, Green) → Red (0/1), Blue (0/1), Green (0/1)

#### Z-Score Normalization (Standardization)
- **Why**: Large-range features dominate distance calculations
- **Problem**: Age (20-60) vs Salary (20,000-200,000)
- **Formula**: z = (x - mean) / SD
- **Result**: All features on same scale (mean=0, SD=1)

#### Importance
- KNN sensitive to feature scales
- Without normalization: High-value features dominate
- Both encoding & normalization crucial for good performance

### KNN as Feature Engineer

#### Beyond Simple Classification
- Use KNN to **create new features**
- For each sample: compute distance to k nearest neighbors
- Use these distances as new features
- Train another model (logistic regression, trees) on original + KNN features
- Model benefits from both global patterns and local patterns

---

## 1.10 DECISION TREES

### Concept

#### Definition
- **Supervised** learning (classification & regression)
- Works like a **flowchart**
- Makes hierarchical decisions

#### Tree Structure
- **Root Node**: First decision/split
- **Internal Nodes**: Questions (Is Age > 30? Is Income > 50k?)
- **Branches**: Outcomes of decision
- **Leaf Nodes**: Final predictions (class label or numeric value)

#### Interpretability
- **Super easy to visualize and explain**
- Non-technical people can understand
- Black-box algorithms (neural networks) harder to explain

### Tree Learning Algorithms

#### CART (Classification And Regression Trees)
- Most common
- Uses Gini impurity for classification
- Uses SSE (Sum of Squared Errors) for regression

#### ID3 (Iterative Dichotomiser 3)
- Uses Information Gain
- Builds top-down
- Older method

#### C4.5
- Extension of ID3
- Handles continuous variables better

#### CHAID (Chi-squared Automatic Interaction Detection)
- Statistical approach
- Tests statistical significance of splits

### How Decision Trees Work: Recursive Partitioning

#### Core Process
1. Start with all data at root
2. Find **best split** (feature & threshold) that maximizes purity
3. Split data into two groups
4. Repeat for each group until stopping condition met
5. Leaves represent final predictions

#### Best Split
- Reduces **impurity** the most
- Impurity = mixture of different classes
- Pure node = all same class

#### Impurity Measures

##### Entropy (Information-based)
- Entropy = 0: All same class (pure)
- Entropy = 1: 50-50 mix (very impure)
- Formula: H = -Σ(p × log(p)) for each class
- Lower entropy = purer

##### Gini Impurity
- Gini = 0: Pure node
- Gini = 0.5: 50-50 mix (most impure)
- Formula: Gini = 1 - Σ(p²) for each class
- Lower Gini = purer

##### Information Gain
- Reduction in entropy after split
- IG = Entropy(parent) - Weighted_Entropy(children)
- Higher IG = better split

### Example: Weather & Golf

- Dataset: Should we play golf based on weather?
- Split by "Weather" feature first (gives highest IG)
  - Sunny → Need further split
  - Overcast → All "Yes" (pure leaf)
  - Rainy → All "Yes" (pure leaf)
- Then split "Sunny" by "Temperature"
  - Hot → "No"
  - Mild → "No"
  - Cool → "Yes"

### Regression Trees

#### Difference from Classification
- Predicts **continuous value** (not category)
- Leaves contain **mean of values** in that partition
- Uses **SSE (Sum of Squared Errors)** instead of information gain
- **Variance reduction**: Pick split minimizing SSE

#### Process
- Same recursive partitioning
- But minimize: Σ(actual - mean)²
- Prediction = Mean of all values reaching that leaf

### Stopping Rules (Prevent Overfitting)

#### Problem: Unchecked Growth
- Tree keeps splitting until perfect fit
- Memorizes training data (overfitting)
- **Overfitting**: High train accuracy, poor test accuracy

#### Stopping Conditions

##### Minimum Node Size
- Stop if partition has < N samples (e.g., 5)
- Avoids tiny leaves that overfit

##### Maximum Depth
- Limit tree height/levels
- Prevents overly complex trees

##### Minimum Information Gain
- Split only if IG > threshold
- Avoids tiny improvements

#### Why Needed
- Without limits: leaf = 1 sample (perfect training fit, terrible testing fit)
- With limits: Better generalization to new data

### Predicting Continuous Values (Regression)

#### Process
1. Recursively split data into groups
2. Each group → similar numeric values
3. Each leaf → **mean of values** in that group

#### Split Selection
- Try all possible splits
- Choose split that **minimizes SSE**
- SSE = Σ(actual - group_mean)²

#### Prediction
- New sample follows path down tree
- Reaches leaf → prediction = mean of that leaf

---

## 1.11 ENSEMBLE METHODS

### Concept

#### Why Ensemble?
- **Single model** can be wrong
- **Multiple models** voting → better accuracy
- "Wisdom of crowds"
- Reduces variance (overfitting)

#### Philosophy
- Many weak learners → one strong learner
- Combine predictions → more robust

### Bagging (Bootstrap Aggregation)

#### Definition
- **Bag** = **Bootstrap + Aggregation**
- Creates multiple datasets by random sampling **with replacement**

#### Process
1. Create many bootstrap samples (n samples each with replacement)
2. Train separate model on each sample (usually decision tree)
3. For classification: Majority vote
4. For regression: Average all predictions

#### Why It Works
- Each bootstrap sample slightly different
- Trees trained on different data → different splits
- Diversity reduces variance
- Average/vote of diverse models = more stable

#### Example
- Original data: 5 students' test scores
- Bootstrap sample 1: [S1, S3, S3, S5, S4] (sampling with replacement)
- Bootstrap sample 2: [S2, S5, S1, S4, S2]
- Bootstrap sample 3: [S4, S5, S3, S1, S1]
- Train model on each
- New prediction: Average or majority vote of 3 models

#### Advantage
- Simple, effective
- Reduces overfitting
- Works with any base model

### Random Forest

#### Definition
- **Bagging + Random Feature Selection**
- Most popular ensemble method
- Uses decision trees as base model

#### Key Difference from Bagging
- Each tree uses **random subset of features** at each split
- Even on same data, trees look different
- More diversity → better accuracy

#### Process
1. Create bootstrap samples (like bagging)
2. For each tree, at each split:
   - Randomly select k features (e.g., √total_features)
   - Find best split among ONLY these k features
3. Grow full tree without pruning
4. For classification: Majority vote across trees
5. For regression: Average predictions

#### Why Feature Randomness Matters
- Without it: Many trees similar → predictions similar
- With it: Trees different → predictions diverse → ensemble better
- Prevents high correlation between trees

#### Example: House Price Prediction
- Features: Size, Rooms, Location, Age, Style
- Tree 1 (features: Size, Rooms) → $155k
- Tree 2 (features: Location, Age) → $160k
- Tree 3 (features: Rooms, Age) → $155k
- Final: Average = $156.7k

#### Variable Importance
- Which features most important for splitting?
- Calculated from total reduction in impurity across all trees
- High importance = feature splits trees often/effectively
- Helps understand model decisions

#### Hyperparameters

| **Parameter** | **Effect** |
|---|---|
| **n_trees** | More trees → better accuracy (diminishing returns) |
| **max_depth** | Deeper → complex model, risk overfitting |
| **min_samples_leaf** | Larger → simpler trees, less overfitting |
| **max_features** | More features per split → less random, might overfit |

### Bagging vs Random Forest

| **Aspect** | **Bagging** | **Random Forest** |
|---|---|---|
| **Sampling** | Bootstrap only | Bootstrap + feature random |
| **Tree Similarity** | Trees may look similar | Trees more diverse |
| **Accuracy** | Good | Often better |
| **Base Model** | Any model | Usually trees |
| **Correlated Trees** | Possible | Less likely |

---

## 1.12 COMMON MISTAKES & MISCONCEPTIONS

### Confusing Concepts

1. **Standard Deviation vs Standard Error**
   - SD: Variability of individual data points
   - SE: Variability of sample statistic (mean)
   - SE = SD / √n (always smaller!)

2. **Bias vs Random Error**
   - Bias: Systematic error (always wrong same direction)
   - Random Error: Unpredictable, averages out

3. **Correlation vs Causation**
   - Correlation: Two variables move together
   - Causation: One causes the other
   - Correlation ≠ Causation!

4. **Confidence Interval Interpretation**
   - WRONG: "95% chance true value is in this interval"
   - RIGHT: "If we repeat sampling, 95% of intervals contain true value"

5. **P-Value Misinterpretation**
   - WRONG: "P = 0.05 means 5% chance hypothesis is wrong"
   - RIGHT: "If hypothesis true, 5% chance of observing this data"

6. **Overfitting vs Underfitting**
   - Overfitting: Model memorizes data (low train error, high test error)
   - Underfitting: Model too simple (high both errors)

---

# 2. ADVANCED CONCEPT EXPLANATIONS

## 2.1 LINEAR REGRESSION DEEP DIVE

### Why It Matters
- Foundation of ML (nearly all complex models use similar ideas)
- Interpretable (can explain predictions)
- Fast to train and predict
- Good baseline model

### How It Really Works (Step-by-Step)

#### Example: Hours Studied vs Test Score

**Data:**
| Hours | Score |
|---|---|
| 2 | 50 |
| 3 | 55 |
| 4 | 70 |
| 5 | 80 |

#### Step 1: Calculate Means
- Mean of X (hours) = (2+3+4+5)/4 = 3.5
- Mean of Y (score) = (50+55+70+80)/4 = 63.75

#### Step 2: Calculate Deviations & Products
For each point, calculate: (x - mean_x) × (y - mean_y) and (x - mean_x)²

| X | Y | (x-3.5) | (y-63.75) | (x-3.5)² | (x-3.5)(y-63.75) |
|---|---|---|---|---|---|
| 2 | 50 | -1.5 | -13.75 | 2.25 | 20.625 |
| 3 | 55 | -0.5 | -8.75 | 0.25 | 4.375 |
| 4 | 70 | 0.5 | 6.25 | 0.25 | 3.125 |
| 5 | 80 | 1.5 | 16.25 | 2.25 | 24.375 |
| | | | Sum: | 5 | 52.5 |

#### Step 3: Calculate Slope
- m = Σ(x-x̄)(y-ȳ) / Σ(x-x̄)²
- m = 52.5 / 5 = 10.5

**Meaning**: For each additional hour studied, score increases by 10.5 points

#### Step 4: Calculate Intercept
- b = ȳ - m × x̄
- b = 63.75 - 10.5 × 3.5
- b = 63.75 - 36.75 = 27

**Meaning**: If someone studied 0 hours, predicted score = 27

#### Step 5: Write Equation
- **Y = 10.5X + 27**

#### Step 6: Make Predictions
- For X = 6 hours: Y = 10.5(6) + 27 = 63 + 27 = 90 points
- For X = 1 hour: Y = 10.5(1) + 27 = 37.5 points

### Real-World Interpretation

**Example: Temperature vs Ice Cream Sales**
- If Y = 0.8X + 20 (where X = temp in °C, Y = sales)
- Slope (0.8): Each degree warmer → 0.8 more ice creams sold
- Intercept (20): If temp = 0°C → 20 ice creams (baseline)

**Reality Check**: Make sense? Higher temp → more sales? Yes! ✓

---

## 2.2 CLASSIFICATION METRICS DEEP DIVE

### Confusion Matrix (Foundation)

```
              Predicted
              Pos  Neg
Actual  Pos  [TP] [FN]
        Neg  [FP] [TN]
```

- **TP** (True Positive): Correctly predicted 1
- **FP** (False Positive): Incorrectly predicted 1 (Type I error)
- **TN** (True Negative): Correctly predicted 0
- **FN** (False Negative): Incorrectly predicted 0 (Type II error)

### Metrics Explained

#### Accuracy
- Formula: (TP + TN) / Total
- "% of predictions correct"
- **Problem**: Misleading if classes imbalanced
- Example: If 99% are healthy, always predicting "healthy" = 99% accuracy!

#### Precision (Positive Predictive Value)
- Formula: TP / (TP + FP)
- "Of all positive predictions, how many actually positive?"
- **Answer**: When model says "Yes", how often correct?
- **Use**: Spam detection (minimize false alarms)
- **Example**: If 100 emails marked spam, 95 truly spam → precision = 95%

#### Recall (Sensitivity / True Positive Rate)
- Formula: TP / (TP + FN)
- "Of all actual positives, how many predicted positive?"
- **Answer**: Did we catch all the positives?
- **Use**: Disease detection (minimize missed cases)
- **Example**: Of 100 actual spam emails, caught 95 → recall = 95%

#### F1 Score
- Formula: 2 × (Precision × Recall) / (Precision + Recall)
- **Harmonic mean** of precision & recall
- Single number balancing both metrics
- Range: 0 to 1 (higher is better)
- **Use**: When precision AND recall both matter equally

### Precision vs Recall Trade-off

**Example: Cancer Detection**
- High Precision, Low Recall: Few false alarms, but miss many real cancers ❌
- Low Precision, High Recall: Catch all cancers, but many false alarms ❌
- Balanced: Good mix ✓

**How to Adjust**: Tuning decision threshold
- Lower threshold → Higher recall (catch more)
- Higher threshold → Higher precision (fewer false alarms)

---

## 2.3 WHY CENTRAL LIMIT THEOREM MATTERS

### The Magic Behind It

#### Problem It Solves
- Population distribution **unknown**
- Can't measure entire population
- Need to estimate from sample

#### Solution
- **CLT guarantees**: Sample mean distribution ≈ normal
- **Even if** population very skewed/weird
- Sample size > 30 usually sufficient

#### Real-World Example
- Population: Incomes in a country (very skewed! Few rich people)
- Sample 100 people, calculate mean income
- Repeat 1000 times with different samples
- Plot of 1000 means → **Bell curve!** (despite skewed population)

#### Practical Use
1. Sample mean is unbiased estimate of population mean
2. Distribution of sample means is approximately normal
3. Can calculate confidence intervals
4. Can do hypothesis testing

---

## 2.4 BOOTSTRAP INTUITION

### Why It's Powerful

#### Traditional Approach Limitations
- Assumes normal distribution
- Needs large sample size
- Math gets complex for weird distributions

#### Bootstrap Magic
- Treat sample as population
- Resample with replacement
- Empirical distribution > theoretical assumptions

#### When It Shines
- Small samples
- Skewed data
- Non-standard statistics (e.g., median, 90th percentile)
- You don't know the distribution

### Practical Example

**Scenario**: Movie rating (1-5 stars)
- Sample of 20 ratings: [5, 4, 5, 3, 4, 5, 2, 5, ...]
- Want: Confidence interval for median rating

**Bootstrap Process**:
1. Resample 20 ratings with replacement from sample
   - Bootstrap sample 1: [5, 5, 4, 2, 5, ...] (some ratings repeated, some missing)
   - Bootstrap sample 2: [4, 3, 5, 5, ...] (different combination)
   - ... repeat 1000 times
2. Calculate median for each bootstrap sample
3. Get 1000 bootstrap medians
4. 95% CI = [2.5th percentile, 97.5th percentile] of bootstrap medians

**Result**: Confidence interval for population median without assuming distribution!

---

## 2.5 TREE-SPLITTING INTUITION

### Entropy Example (Golf Dataset)

**Start**: 3 Yes, 3 No (mixed)
- Entropy = 1 (max impurity)

**After splitting by Weather**:
- Sunny: 2 Yes, 2 No → Entropy = 1 (still mixed!)
- Overcast: 2 Yes, 0 No → Entropy = 0 (pure)
- Rainy: 1 Yes, 1 No → Entropy = 1 (mixed)
- Weighted entropy = (2/6)×1 + (2/6)×0 + (2/6)×1 = 0.67

**Information Gain** = 1 - 0.67 = 0.33

**If we split by another feature**, might get IG = 0.15

**Decision**: Choose Weather (IG = 0.33 > 0.15) ✓

### Visualizing Gini Impurity

- All Class A → Gini = 0 (pure) ✓ Perfect for predictions
- 50-50 mix → Gini = 0.5 (most mixed) ✗ No idea which class
- 75-25 mix → Gini = 0.375 (reasonably pure) ~ Okay

---

# 3. EXAM WEIGHT ANALYSIS

## ⭐⭐⭐⭐⭐ EXTREMELY HIGH WEIGHT (Must Know!)

1. **Linear Regression (Simple + Multiple)**
   - Appears in ~30% of exams
   - Foundation for all regression
   - Formulas, slope, intercept, predictions

2. **Classification vs Regression**
   - Fundamental ML distinction
   - Appears in classification questions
   - When to use which?

3. **Decision Trees & Random Forest**
   - Popular for exams
   - Tree building, splits, overfitting
   - Bagging concept

4. **Logistic Regression**
   - Binary classification foundation
   - Sigmoid function, probability
   - Very likely exam question

5. **Central Limit Theorem**
   - Statistical foundation
   - Confidence intervals based on this
   - Must-know concept

---

## ⭐⭐⭐⭐ VERY HIGH WEIGHT

1. **Supervised Learning Overview**
   - Types, examples, when to use

2. **K-NN Algorithm**
   - How it works, choosing k
   - Distance metrics

3. **Confusion Matrix & Metrics**
   - Accuracy, precision, recall, F1
   - Very common exam questions

4. **Sampling & Bias**
   - Selection bias, random sampling
   - Why bias matters

5. **Naïve Bayes**
   - Bayes' theorem, conditional probability
   - When it works well

6. **Data Types (Numeric vs Categorical)**
   - Foundation of EDA
   - Essential for preprocessing

---

## ⭐⭐⭐ HIGH WEIGHT

1. **Standard Deviation vs Standard Error**
   - Common confusion point
   - Will definitely ask

2. **Percentiles & Quartiles**
   - Visualization, interpretation
   - Used in boxplot questions

3. **Bootstrap Method**
   - Resampling, confidence intervals
   - Increasingly popular

4. **Overfitting & Underfitting**
   - Decision tree context
   - Model evaluation

5. **Correlation Coefficient (Pearson's r)**
   - Range, interpretation
   - Relationship vs causation

6. **Confidence Intervals**
   - Calculation, interpretation
   - Very common

---

## ⭐⭐ MEDIUM WEIGHT

1. **Regularization** (Ridge, Lasso)
   - Multiple regression context
   - Preventing overfitting

2. **Feature Engineering**
   - One-hot encoding
   - Normalization/Standardization

3. **Distributions** (Normal, t, Binomial, etc.)
   - Properties, when used
   - Less detail, more conceptual

4. **Ensemble Methods Details**
   - Beyond just Random Forest

5. **Multi-class Logistic Regression**
   - Softmax function

---

## ⭐ LOW WEIGHT

1. **Specific algorithms** (SVM, XGBoost details)
   - Mentioned but not deeply tested

2. **Advanced preprocessing**
   - Time series, spatial data

3. **Mathematical proofs**
   - Derivations usually not asked

4. **Historical context**
   - When algorithms developed

---

# 4. FORMULA INTELLIGENCE MODULE

## Key Formulas with Explanations

### Slope (Linear Regression)
```
m = Σ(x - x̄)(y - ȳ) / Σ(x - x̄)²
```
- **What it does**: Finds how much Y changes per unit X
- **Variables**:
  - x, y = individual data points
  - x̄, ȳ = means
  - Σ = sum across all points
- **Purpose**: Determining direction & steepness of best-fit line
- **When to use**: Simple linear regression
- **Example**: m = 2.5 means Y increases 2.5 units per unit increase in X

---

### Y-Intercept (Linear Regression)
```
b = ȳ - m × x̄
```
- **What it does**: Finds where line crosses Y-axis
- **Variables**:
  - ȳ = mean of Y values
  - m = slope (calculated above)
  - x̄ = mean of X values
- **Purpose**: Complete the equation Y = mX + b
- **When to use**: After calculating slope
- **Example**: If ȳ=50, m=3, x̄=10 → b = 50 - 3×10 = 20

---

### Cost Function (Mean Squared Error)
```
J(θ) = (1/2m) × Σ[hθ(x) - y]²
```
- **What it does**: Measures how far predictions are from actual values
- **Variables**:
  - m = number of training examples
  - hθ(x) = predicted value
  - y = actual value
  - Σ = sum across all examples
- **Purpose**: Quantify model error (lower is better)
- **When to use**: Evaluating regression models
- **Example**: If predictions are [5, 5, 5] and actuals are [4, 5, 6], error = (1+0+1)/2 = 1

---

### Standard Error (SE)
```
SE = SD / √n
```
- **What it does**: Measures variability of sample mean
- **Variables**:
  - SD = standard deviation of sample
  - n = sample size
- **Purpose**: Estimate precision of sample mean
- **When to use**: Creating confidence intervals
- **Example**: SD=10, n=100 → SE = 10/10 = 1

---

### Pearson Correlation Coefficient
```
r = Σ[(x - x̄)(y - ȳ)] / √[Σ(x - x̄)² × Σ(y - ȳ)²]
```
- **What it does**: Measures linear relationship strength
- **Variables**:
  - x, y = data points
  - x̄, ȳ = means
- **Purpose**: Quantify how variables move together
- **Range**: -1 to +1
- **When to use**: Correlation analysis
- **Interpretation**:
  - r = 1: Perfect positive
  - r = 0: No linear relationship
  - r = -1: Perfect negative

---

### Confidence Interval (for Mean)
```
CI = X̄ ± (z × SE)
```
- **What it does**: Creates range around sample mean
- **Variables**:
  - X̄ = sample mean
  - z = critical value (1.96 for 95%, 2.58 for 99%)
  - SE = standard error
- **Purpose**: Estimate population mean with confidence level
- **When to use**: After calculating sample statistics
- **Example**: Mean=50, SE=2, 95% CI = 50 ± (1.96×2) = [46.08, 53.92]

---

### Information Gain (Entropy-based)
```
IG = H(parent) - Σ[|subset|/|parent| × H(subset)]
```
- **What it does**: Measures improvement in purity after split
- **Variables**:
  - H = entropy
  - |subset| = size of child node
  - |parent| = size of parent node
- **Purpose**: Choose best split in decision trees
- **When to use**: Tree building
- **Higher IG**: Better split

---

### Entropy (Information Theory)
```
H = -Σ(p × log₂(p))
```
- **What it does**: Measures randomness/impurity
- **Variables**:
  - p = probability of each class
  - Σ = sum across all classes
- **Purpose**: Quantify how "mixed" a node is
- **Range**: 0 (pure) to 1 (completely mixed)
- **When to use**: Building decision trees with ID3/C4.5

---

### Gini Impurity
```
Gini = 1 - Σ(pᵢ²)
```
- **What it does**: Measures impurity (different from entropy)
- **Variables**:
  - pᵢ = probability of class i
  - Σ = sum across all classes
- **Purpose**: Choose splits in CART algorithm
- **Range**: 0 (pure) to 0.5 (most impure)
- **When to use**: Building decision trees

---

### Precision
```
Precision = TP / (TP + FP)
```
- **What it does**: Of predicted positives, how many correct?
- **Purpose**: Minimize false alarms
- **When to use**: Spam detection, fraud prevention
- **Example**: Of 100 predicted spam, 95 truly spam → Precision = 95%

---

### Recall (Sensitivity)
```
Recall = TP / (TP + FN)
```
- **What it does**: Of actual positives, how many caught?
- **Purpose**: Minimize missed cases
- **When to use**: Disease detection, security threats
- **Example**: Of 100 actual diseases, caught 95 → Recall = 95%

---

### F1 Score
```
F1 = 2 × (Precision × Recall) / (Precision + Recall)
```
- **What it does**: Harmonic mean of precision & recall
- **Purpose**: Single balanced metric
- **Range**: 0 to 1 (higher better)
- **When to use**: Imbalanced classes
- **Example**: Precision=0.9, Recall=0.8 → F1 = 2×(0.72)/(1.7) ≈ 0.84

---

### R-Squared (Coefficient of Determination)
```
R² = 1 - (SS_res / SS_tot)
```
- **What it does**: Proportion of variance explained
- **Variables**:
  - SS_res = residual sum of squares
  - SS_tot = total sum of squares
- **Purpose**: Evaluate regression model goodness-of-fit
- **Range**: 0 to 1 (higher better)
- **Interpretation**: R² = 0.85 means model explains 85% of variation

---

### Sigmoid Function
```
σ(z) = 1 / (1 + e^(-z))
```
- **What it does**: Converts any value to probability [0, 1]
- **Purpose**: Output for logistic regression
- **Properties**:
  - σ(0) = 0.5
  - σ(∞) → 1
  - σ(-∞) → 0
- **When to use**: Classification with probability output

---

### Bayes' Theorem
```
P(y|X) = [P(X|y) × P(y)] / P(X)
```
- **What it does**: Reverses conditional probability
- **Variables**:
  - P(y|X) = posterior (what we want)
  - P(X|y) = likelihood
  - P(y) = prior
  - P(X) = evidence
- **Purpose**: Foundation of Naïve Bayes
- **When to use**: Classification with probability-based methods

---

### Euclidean Distance
```
d = √[(x₁-x₂)² + (y₁-y₂)²]
```
- **What it does**: Straight-line distance between points
- **Purpose**: K-NN nearest neighbor calculation
- **Extends to**: d = √[Σ(xᵢ-yᵢ)²] for multiple dimensions
- **When to use**: Distance-based algorithms

---

### Manhattan Distance
```
d = |x₁-x₂| + |y₁-y₂|
```
- **What it does**: "Taxi cab" distance (grid paths)
- **Purpose**: Alternative to Euclidean
- **When to use**: Grid-like data, less sensitive to outliers

---

### Z-Score (Standardization)
```
z = (x - mean) / SD
```
- **What it does**: Converts to standard normal (mean=0, SD=1)
- **Purpose**: Normalize features to same scale
- **When to use**: K-NN, neural networks, distance-based methods
- **Result**: All features equally contribute to distance

---

## Formula Cheat Sheet (At a Glance)

| **Concept** | **Formula** | **When Used** |
|---|---|---|
| Slope | m = Σ(x-x̄)(y-ȳ)/Σ(x-x̄)² | Linear regression |
| Intercept | b = ȳ - m×x̄ | Linear regression |
| MSE | (1/2m)Σ(ŷ-y)² | Model evaluation |
| SE | SD/√n | Confidence intervals |
| Correlation | r = Σ(x-x̄)(y-ȳ)/√[Σ(x-x̄)²Σ(y-ȳ)²] | Relationship strength |
| CI | X̄ ± z×SE | Population estimate |
| IG | H(parent) - Σp×H(child) | Tree splitting |
| Gini | 1 - Σpᵢ² | Tree impurity |
| Precision | TP/(TP+FP) | Classification |
| Recall | TP/(TP+FN) | Classification |
| F1 | 2×P×R/(P+R) | Balanced metric |
| Sigmoid | 1/(1+e^(-z)) | Logistic regression |
| Bayes | P(y\|X)=P(X\|y)P(y)/P(X) | Naïve Bayes |

---

# 5. SMART REVISION NOTES (COMPRESSED)

## One-Page Study Survival Guide

### DATA TYPES
- **Numeric**: Continuous (any value) or Discrete (integers)
- **Categorical**: Nominal (no order), Binary (2 values), Ordinal (ranked)

### CENTRAL TENDENCY
- **Mean**: Average, sensitive to outliers
- **Median**: Middle value, robust
- **Trimmed Mean**: Remove extremes, compromise
- **Mode**: Most frequent value

### SPREAD
- **Variance/SD**: Spread from mean (sensitive to outliers)
- **IQR**: Q3 - Q1 (robust)
- **Percentile**: X% of data below this value

### CORRELATION
- **Pearson's r**: -1 to +1 (linear only)
- **0.5 to 1**: Strong positive
- **-1 to -0.5**: Strong negative
- **Close to 0**: Weak/no linear relationship

### SAMPLING
- **Random Sampling**: Each element equal chance (unbiased)
- **Bias**: Systematic error in one direction
- **Selection Bias**: Skewed data collection
- **Regression to Mean**: Extremes followed by averages (luck fades)

### DISTRIBUTIONS
- **Normal**: Bell curve, mean=median=mode
- **t-Distribution**: Like normal but fatter tails (small samples)
- **Binomial**: Success/failure outcomes
- **Chi-Square**: Categorical data testing
- **Poisson**: Count of events

### CLT & SAMPLING
- **CLT**: Sample means ≈ normal (even if population skewed)
- **SE**: SD/√n (bigger sample → smaller SE)
- **Confidence Interval**: X̄ ± 1.96×SE (95% confident)
- **Bootstrap**: Resample with replacement for empirical distribution

### MACHINE LEARNING TYPES
- **Supervised**: Labeled data, predict known output
  - Classification: Predict categories
  - Regression: Predict continuous numbers
- **Unsupervised**: No labels, find patterns
  - Clustering: Group similar items
- **Semi-Supervised**: Mix labeled + unlabeled

### LINEAR REGRESSION
- **Equation**: Y = mX + b
- **Slope m**: Change in Y per unit X
- **Intercept b**: Y value when X=0
- **Best fit**: Minimize sum of squared errors
- **Cost Function**: (1/2m)Σ(predicted-actual)²
- **R²**: % of variance explained (0-1, higher better)

### LOGISTIC REGRESSION
- **Output**: Probability [0-1] (not direct Y value)
- **Sigmoid**: S-curve squashing function
- **Decision**: P≥0.5 → Class 1, else Class 0
- **Cost**: Log loss (penalizes confident wrong predictions)
- **Multi-class**: Use Softmax instead of sigmoid

### K-NN
- **Process**: Find k nearest neighbors → vote/average
- **k Choice**: Small k→overfitting, Large k→underfitting
- **Distance**: Euclidean (√(Δx²+Δy²)) or Manhattan (|Δx|+|Δy|)
- **Preprocessing**: Normalize features (z-score) & encode categorical
- **Lazy**: No training phase, just remembers data

### DECISION TREES
- **Split**: Choose feature/threshold minimizing impurity
- **Impurity**: Entropy (0-1) or Gini (0-0.5)
- **IG**: Reduction in impurity (higher→better split)
- **Overfitting**: Unchecked growth memorizes data
- **Stopping**: Min node size, max depth, min IG gain
- **Regression**: Predict mean of values in leaf

### RANDOM FOREST
- **Bootstrap**: Create multiple datasets (with replacement)
- **Random Features**: Each tree uses random feature subset
- **Diversity**: Different trees→different errors→accurate ensemble
- **Classification**: Majority vote
- **Regression**: Average predictions
- **Variable Importance**: Which features split most/effectively

### NAÏVE BAYES
- **Bayes**: P(y|X) = P(X|y)×P(y)/P(X)
- **Naive Assumption**: Features conditionally independent (usually false but works!)
- **Training**: Build probability tables
- **Prediction**: Calculate P(class|data) for each class → choose max
- **Types**: Gaussian (continuous), Multinomial (counts), Bernoulli (binary)

### CLASSIFICATION METRICS
- **TP/FP/TN/FN**: Confusion matrix elements
- **Accuracy**: (TP+TN)/Total (misleading if imbalanced)
- **Precision**: TP/(TP+FP) [of predicted 1s, how many correct?]
- **Recall**: TP/(TP+FN) [of actual 1s, how many caught?]
- **F1**: 2×P×R/(P+R) [balanced metric]

### OVERFITTING vs UNDERFITTING
- **Overfitting**: High train acc, low test acc (memorized)
- **Underfitting**: High both errors (too simple)
- **Regularization**: Add penalty for complex models
- **Solution**: Early stopping, max depth, min samples, cross-validation

### COMMON MISTAKES
- **SD vs SE**: SD is spread of data, SE is spread of mean (SE smaller!)
- **CI Interpretation**: NOT 95% chance value in interval, but 95% of intervals contain it
- **Correlation ≠ Causation**: Can move together without one causing other
- **Bias ≠ Error**: Bias is systematic, error is random

### MEMORY TRIGGERS
- **EDA**: Location (where?) + Variability (how spread?)
- **Sampling**: Random? Biased? Size matters but quality more!
- **CLT**: "Big samples → bell curve" (even if original skewed)
- **ML**: Supervised=labeled, Unsupervised=unlabeled, Semi=mix
- **Trees**: Split→purify, Bag→stabilize, Forest→randomize+bag

---

# 6. DEMO EXAM PAPER & SOLUTIONS

## FULL EXAM (3 Hours)

### SECTION A: MULTIPLE CHOICE (10 Questions × 2 marks = 20 marks)

**Q1. What is the primary difference between continuous and discrete numeric data?**

A) Continuous has labels, discrete doesn't
B) Continuous takes any value in range; discrete takes specific integers
C) Continuous is categorical; discrete is numeric
D) There is no difference

**✓ Correct Answer: B**
**Explanation**: Continuous data (height, temperature) can be any value. Discrete (clicks, counts) are integers.

---

**Q2. The standard error of the mean is:**

A) The same as standard deviation
B) Standard deviation divided by √n
C) Always larger than standard deviation
D) Used to measure individual data point spread

**✓ Correct Answer: B**
**Explanation**: SE = SD/√n. Larger samples → smaller SE (more precise estimate).

---

**Q3. In linear regression Y = 3X + 5, what does the 5 represent?**

A) Slope
B) The number of data points
C) Y-intercept
D) Correlation coefficient

**✓ Correct Answer: C**
**Explanation**: The constant term (5) is where the line crosses the Y-axis (when X=0).

---

**Q4. Which distance metric is "taxi cab" distance?**

A) Euclidean
B) Manhattan
C) Minkowski
D) Gaussian

**✓ Correct Answer: B**
**Explanation**: Manhattan = |x₁-x₂| + |y₁-y₂| (grid paths). Euclidean = straight line.

---

**Q5. What is the purpose of z-score normalization in K-NN?**

A) Remove outliers
B) Convert features to same scale (mean=0, SD=1)
C) Calculate accuracy
D) Balance classes

**✓ Correct Answer: B**
**Explanation**: Large-range features dominate distance. Normalization prevents this.

---

**Q6. In a decision tree, what does information gain measure?**

A) How many data points we gain
B) Reduction in impurity after split
C) The depth of the tree
D) Accuracy of predictions

**✓ Correct Answer: B**
**Explanation**: IG = Entropy(parent) - Weighted_Entropy(children). Higher IG = better split.

---

**Q7. What is the key assumption in Naïve Bayes?**

A) All data is normally distributed
B) Features are conditionally independent given class
C) Classes are equally likely
D) All features equally important

**✓ Correct Answer: B**
**Explanation**: Despite being "naive" (usually false), it works surprisingly well!

---

**Q8. Which metric is best when classes are imbalanced?**

A) Accuracy
B) Precision only
C) Recall only
D) F1 Score

**✓ Correct Answer: D**
**Explanation**: F1 balances precision & recall. Accuracy misleading with imbalanced classes.

---

**Q9. Random Forest differs from Bagging by:**

A) Random Forest uses bootstrap sampling
B) Random Forest uses random feature selection at each split
C) Bagging uses decision trees
D) They are identical

**✓ Correct Answer: B**
**Explanation**: Random Forest = Bagging + random feature selection = more diversity.

---

**Q10. What does Central Limit Theorem state?**

A) Population must be normal
B) Sample means approximately normal for large samples (even if population skewed)
C) All samples have same mean
D) Sampling always introduces bias

**✓ Correct Answer: B**
**Explanation**: CLT allows confidence intervals without knowing population distribution.

---

### SECTION B: SHORT ANSWER (5 Questions × 4 marks = 20 marks)

**Q11. Define overfitting and explain how to prevent it in decision trees.**

**Answer** (4 marks):
- **Definition** (1 mark): Model learns training data too well, including noise. High train accuracy, poor test accuracy. Memorizes instead of generalizes.
- **Prevention Methods** (3 marks):
  - Set minimum node size (stop splitting if <N samples)
  - Set maximum depth (limit tree height)
  - Require minimum information gain for split
  - Use cross-validation to monitor test performance
  - Prune tree after growth (remove weak splits)

---

**Q12. Calculate the Pearson correlation coefficient for this data:**

| X | 1 | 2 | 3 | 4 |
|Y | 2 | 4 | 5 | 7 |

**Answer** (4 marks):

Step 1: Calculate means (1 mark)
- x̄ = (1+2+3+4)/4 = 2.5
- ȳ = (2+4+5+7)/4 = 4.5

Step 2: Calculate components (2 marks)
| X | Y | (x-2.5) | (y-4.5) | (x-2.5)² | (y-4.5)² | (x-2.5)(y-4.5) |
|---|---|---|---|---|---|---|
| 1 | 2 | -1.5 | -2.5 | 2.25 | 6.25 | 3.75 |
| 2 | 4 | -0.5 | -0.5 | 0.25 | 0.25 | 0.25 |
| 3 | 5 | 0.5 | 0.5 | 0.25 | 0.25 | 0.25 |
| 4 | 7 | 1.5 | 2.5 | 2.25 | 6.25 | 3.75 |
| | | | Sum: | 5 | 13 | 8 |

Step 3: Apply formula (1 mark)
r = Σ(x-x̄)(y-ȳ) / √[Σ(x-x̄)² × Σ(y-ȳ)²]
r = 8 / √(5 × 13) = 8 / √65 = 8 / 8.06 ≈ **0.99**

**Interpretation**: Very strong positive correlation (nearly perfect)

---

**Q13. Explain the difference between precision and recall with an example.**

**Answer** (4 marks):

**Precision** (2 marks):
- Formula: TP/(TP+FP)
- Meaning: "Of all positive predictions, how many actually positive?"
- Use: Minimize false alarms (spam detection)
- Example: If email marked 100 messages as spam and 95 truly spam → Precision = 95%

**Recall** (2 marks):
- Formula: TP/(TP+FN)
- Meaning: "Of all actual positives, how many predicted positive?"
- Use: Minimize missed cases (disease detection)
- Example: Of 100 actual spam messages, caught 95 → Recall = 95%

**Trade-off**: High precision + low recall = miss many cases. Low precision + high recall = many false alarms.

---

**Q14. What is the Bootstrap method and why is it useful?**

**Answer** (4 marks):

**Definition** (2 marks):
- Resampling technique
- Take original sample as "population"
- Draw many new samples WITH REPLACEMENT
- Compute statistic (mean, median, etc.) for each resample
- Distribution of statistics ≈ sampling distribution

**Process Example**:
1. Original sample: 10 values
2. Draw 1000 bootstrap samples (each n=10, sampled with replacement)
3. Calculate mean of each
4. Get 1000 bootstrap means

**Why Useful** (2 marks):
- Works without assuming normal distribution
- Works with small samples
- Works with skewed data
- Estimate standard error & confidence intervals
- No complex math needed, just computation

---

**Q15. Describe how K-NN algorithm works (steps and hyperparameters).**

**Answer** (4 marks):

**Steps** (2 marks):
1. Choose k (number of neighbors)
2. Calculate distance from new point to ALL training points
3. Find k points with smallest distances
4. For classification: Majority vote (most common class)
   For regression: Average of k values

**Hyperparameter: k Choice** (1 mark):
- Small k: Sensitive to noise, overfitting
- Large k: Smooth boundaries, underfitting
- Optimal k: Found via cross-validation

**Preprocessing** (1 mark):
- Normalize features (z-score) so all on same scale
- One-hot encode categorical variables
- Important because algorithm uses distance (sensitive to scale)

---

### SECTION C: LONG ANSWER (3 Questions × 12 marks = 36 marks)

**Q16. Build a simple decision tree for the following dataset:**

**Dataset:**
| Weather | Temp | Play Golf |
|---|---|---|
| Sunny | Hot | No |
| Sunny | Mild | No |
| Sunny | Cool | Yes |
| Rainy | Mild | Yes |
| Rainy | Cool | Yes |
| Overcast | Mild | Yes |

**Questions:**
a) Calculate entropy at root (all 6 samples)
b) Calculate information gain for splitting by "Weather"
c) Draw the resulting tree
d) What would be your prediction for: Weather=Overcast, Temp=Mild?

**Answer** (12 marks):

**Part a) Root Entropy** (3 marks):
- Count: 4 "Yes", 2 "No"
- p(Yes) = 4/6 = 0.667, p(No) = 2/6 = 0.333
- H = -[0.667×log₂(0.667) + 0.333×log₂(0.333)]
- H = -[0.667×(-0.585) + 0.333×(-1.585)]
- H ≈ -[-0.39 - 0.528] = **0.918**

**Part b) Information Gain for "Weather"** (5 marks):

After splitting by Weather:
- **Sunny** (3 samples): 1 Yes, 2 No → H = -[1/3×log₂(1/3) + 2/3×log₂(2/3)] ≈ 0.918
- **Rainy** (2 samples): 2 Yes, 0 No → H = 0 (pure)
- **Overcast** (1 sample): 1 Yes, 0 No → H = 0 (pure)

Weighted entropy after split:
= (3/6)×0.918 + (2/6)×0 + (1/6)×0 = 0.459

IG = 0.918 - 0.459 = **0.459** ✓

(Alternative: If split by Temp, would get IG ≈ 0.25, so Weather is better)

**Part c) Tree Structure** (2 marks):
```
                [Weather]
               /    |    \
           Sunny  Rainy  Overcast
             |      |        |
           [Temp]   Yes      Yes
          /    \
        Hot   Cool/Mild
         |       |
        No      Yes
```

**Part d) Prediction for Overcast & Mild** (2 marks):
- Follow "Weather" → Overcast branch
- Reaches leaf → **"Yes"**
- (No further splits needed on Overcast branch)

---

**Q17. Explain Logistic Regression: concept, sigmoid function, and how it differs from Linear Regression.**

**Answer** (12 marks):

**Concept** (3 marks):
- Supervised classification algorithm
- For binary classification (2 classes)
- Predicts PROBABILITY that X belongs to class 1
- Output always between 0 and 1
- Decision rule: P ≥ 0.5 → Class 1, else Class 0
- Real-world: Email phishing, disease presence, loan default

**Sigmoid Function** (4 marks):
- Formula: σ(z) = 1 / (1 + e^(-z))
- "S-shaped" curve that squashes any input to [0,1]
- Properties:
  - σ(0) = 0.5
  - As z → ∞: σ(z) → 1
  - As z → -∞: σ(z) → 0
  - Smooth, differentiable (good for optimization)
- Process: Linear combination z = θ₀ + θ₁X₁ + θ₂X₂ + ... → Apply sigmoid → Probability

**Differences from Linear Regression** (5 marks):

| Aspect | Linear Regression | Logistic Regression |
|---|---|---|
| **Output** | Any continuous value | Probability [0-1] |
| **Problem Type** | Regression | Classification |
| **Function** | Linear: Y = mX + b | Non-linear: sigmoid(z) |
| **Cost Function** | MSE: (1/2m)Σ(ŷ-y)² | Log Loss: -(1/m)Σ[y×log(ŷ) + (1-y)×log(1-ŷ)] |
| **Output Interpretation** | Predicted value (can be <0 or >100) | Probability (0-1, meaningful) |
| **Decision Rule** | No threshold (continuous output) | Threshold at 0.5 (or tunable) |

**Key Insight**: Logistic regression is NOT a regression algorithm! Despite name, it's a classifier. Uses sigmoid to convert regression-like output to probability.

---

**Q18. Compare Random Forest and Bagging algorithms. Include advantages, disadvantages, when to use each.**

**Answer** (12 marks):

**Bagging (Bootstrap Aggregation)** (4 marks):

**How It Works**:
1. Create multiple bootstrap samples (with replacement)
2. Train separate model on each sample
3. For classification: Majority vote
4. For regression: Average predictions

**Advantages**:
- Reduces variance (overfitting)
- Works with any base model
- Simple to understand & implement
- Parallelizable (train models independently)

**Disadvantages**:
- Trees may look similar (limited diversity)
- Less accurate than Random Forest
- Still requires pruning/stopping rules

---

**Random Forest** (4 marks):

**How It Works**:
1. Create bootstrap samples (like bagging)
2. AT EACH SPLIT: Randomly select k features
3. Find best split among ONLY these k features
4. Grow full trees (no pruning)
5. Aggregate predictions (vote/average)

**Key Difference from Bagging**: Uses random feature selection → More diverse trees

**Advantages**:
- Higher accuracy than bagging (more diversity)
- Handles high-dimensional data well
- Feature importance ranking
- Robust to outliers
- Often good without tuning

**Disadvantages**:
- Less interpretable than single tree
- Slower prediction (many trees)
- Overfitting if too many trees
- Memory intensive

---

**Comparison Table** (4 marks):

| Feature | Bagging | Random Forest |
|---|---|---|
| Sampling | Bootstrap only | Bootstrap + random features |
| Tree Diversity | Limited | High |
| Feature Correlation | Trees can be correlated | Less correlated |
| Accuracy | Good | Often better |
| Interpretability | Single tree simple | Forest complex |
| Default Parameters | Need tuning | Often good as-is |
| Use Case | Baseline, general | Higher accuracy needed |

**When to Use Each**:
- **Bagging**: When you want simplicity & interpretability of individual trees
- **Random Forest**: When you prioritize accuracy & can afford complexity

**Real Example**:
- **Bagging**: Predicting house price (interpretability important)
- **Random Forest**: Spam detection (accuracy most important, complexity acceptable)

---

### SECTION D: NUMERICAL PROBLEM (2 Questions × 8 marks = 16 marks)

**Q19. Confidence Interval Calculation:**

A sample of 100 customers has average spending = $500 with SD = $40.

a) Calculate 95% confidence interval for population mean
b) Calculate 99% confidence interval
c) Interpret both intervals
d) What sample size needed for SE = $2?

**Answer** (8 marks):

**Part a) 95% CI** (2 marks):
- SE = SD / √n = 40 / √100 = 40 / 10 = $4
- 95% CI uses z = 1.96
- CI = $500 ± (1.96 × $4)
- CI = $500 ± $7.84
- **CI = [$492.16, $507.84]**

**Part b) 99% CI** (2 marks):
- Same SE = $4
- 99% CI uses z = 2.58
- CI = $500 ± (2.58 × $4)
- CI = $500 ± $10.32
- **CI = [$489.68, $510.32]**

**Part c) Interpretation** (2 marks):
- 95% CI: "We are 95% confident the true population mean spending is between $492.16 and $507.84"
- 99% CI: "We are 99% confident the true population mean spending is between $489.68 and $510.32"
- **Note**: Higher confidence → wider interval (trade-off)

**Part d) Sample Size for SE = $2** (2 marks):
- Formula: SE = SD / √n
- $2 = $40 / √n
- √n = $40 / $2 = 20
- n = 400
- **Need 400 samples** (4× larger sample for 2× smaller SE)

---

**Q20. Naïve Bayes Classification:**

**Dataset**: Email spam classification
- Total emails: 100 (70 Ham, 30 Spam)
- Feature "Contains Money": 
  - Ham emails: 10 have "money", 60 don't
  - Spam emails: 25 have "money", 5 don't

Predict for new email containing "money": Spam or Ham?

**Answer** (8 marks):

**Step 1: Prior Probabilities** (2 marks):
- P(Ham) = 70/100 = 0.7
- P(Spam) = 30/100 = 0.3

**Step 2: Likelihoods** (3 marks):
- P(Money | Ham) = 10/70 ≈ 0.143
- P(Money | Spam) = 25/30 ≈ 0.833

**Step 3: Posterior Calculations** (2 marks):

P(Ham | Money) ∝ P(Money | Ham) × P(Ham)
= 0.143 × 0.7 = 0.10

P(Spam | Money) ∝ P(Money | Spam) × P(Spam)
= 0.833 × 0.3 = 0.25

**Step 4: Normalization & Prediction** (1 mark):
- P(Spam | Money) = 0.25 / (0.10 + 0.25) = 0.25 / 0.35 ≈ 0.714
- P(Ham | Money) = 0.10 / 0.35 ≈ 0.286

**Prediction: SPAM** ✓ (0.714 > 0.286)

**Interpretation**: Given "money" in email, 71% chance it's spam, 29% chance it's ham. The presence of "money" strongly indicates spam.

---

### SECTION E: CASE STUDY (1 Question × 8 marks = 8 marks)

**Q21. You're building a model to predict customer churn (will customer leave in next month?). You have data on 1000 customers (150 churned, 850 didn't).**

**Scenario**: 
- Model 1: Accuracy = 85%, Precision = 40%, Recall = 90%
- Model 2: Accuracy = 87%, Precision = 80%, Recall = 50%

a) Which model is better? Justify with business context.
b) What's the problem with using accuracy as sole metric here?
c) If you had to choose one metric to optimize, which would it be and why?
d) Suggest how to improve the chosen model.

**Answer** (8 marks):

**Part a) Which Model Better?** (2 marks):

**Model 1 is better for business.**

Justification (1 mark for reasoning):
- Business priority: Don't lose customers (catch all churners)
- High recall (90%) catches most churners → interventions can reach them
- Lower precision (40%) means false alarms, but cost of missing churn > cost of wasted intervention
- Model 1 identifies 90% of churning customers
- Model 2 only identifies 50%

**Part b) Problem with Accuracy** (2 marks):

**Accuracy is misleading here because**:
- Dataset imbalanced: 850/1000 (85%) didn't churn
- A dummy model predicting "no churn" for everyone gets 85% accuracy (but catches 0% of actual churners!)
- Accuracy doesn't reflect business goal: predict who WILL churn
- Better metrics: Recall (catch churners) & Precision (avoid false alarms)

**Part c) Metric to Optimize** (2 marks):

**Optimize RECALL** (with Precision check)

Reasoning:
- Business goal: Identify customers likely to churn
- Recall = catch what percentage of actual churners
- 90% recall = flag 90 out of 100 churners
- Can then offer interventions (discounts, offers) to these customers
- Cost of missing churn > cost of false alarms
- Secondary check: Keep precision > 30% (avoid overwhelming offers to non-churners)

**Part d) Improve Model** (2 marks):

**Strategies**:
1. **Adjust decision threshold**: Lower from 0.5 to 0.3 → predict "churn" more often → higher recall
2. **Class weighting**: Penalize false negatives more (missing churners)
3. **Collect better features**: Add usage frequency, satisfaction score, previous complaints
4. **Ensemble methods**: Combine multiple models for robustness
5. **Cost-based learning**: Explicitly set cost of FN (missed churn) >> cost of FP (false alarm)

---

### SECTION F: TRUE/FALSE (6 Questions × 1 mark = 6 marks)

**Q22. Correlation coefficient of 0.7 proves that variable A causes variable B.** 
**Answer: FALSE** 
Explanation: Correlation measures association only, not causation. Many variables can be correlated without one causing the other.

---

**Q23. Standard error is always smaller than standard deviation.**
**Answer: TRUE**
Explanation: SE = SD/√n. Since √n > 1, SE < SD always.

---

**Q24. In K-NN, k=1 always gives best results.**
**Answer: FALSE**
Explanation: k=1 overfits (sensitive to noise). Large k underfits. Optimal k found via cross-validation.

---

**Q25. Logistic regression outputs predicted probability values between 0 and 1.**
**Answer: TRUE**
Explanation: Sigmoid function squashes output to [0,1].

---

**Q26. Bagging and Random Forest produce identical results.**
**Answer: FALSE**
Explanation: Random Forest uses random feature selection + bootstrap (more diverse). Bagging uses bootstrap only.

---

**Q27. A 95% confidence interval means 95% chance the true value is in this interval.**
**Answer: FALSE**
Explanation: The true value either is or isn't in the interval. The 95% refers to the long-run proportion of such intervals that contain the true value.

---

## ANSWER KEY SUMMARY

| Question | Type | Answer | Difficulty |
|---|---|---|---|
| Q1-10 | MCQ | See explanations | Medium |
| Q11 | Short | Overfitting definition + prevention methods | Medium |
| Q12 | Numerical | r ≈ 0.99 | Hard |
| Q13 | Short | Precision vs Recall | Medium |
| Q14 | Short | Bootstrap explanation | Medium |
| Q15 | Short | K-NN steps | Easy |
| Q16 | Long | Decision tree build | Hard |
| Q17 | Long | Logistic regression | Hard |
| Q18 | Long | RF vs Bagging | Hard |
| Q19 | Numerical | CI calculations | Medium |
| Q20 | Numerical | Naïve Bayes | Hard |
| Q21 | Case Study | Model selection + strategies | Hard |
| Q22-27 | T/F | See answers | Easy-Medium |

## MARKS DISTRIBUTION
- Multiple Choice: 20 marks
- Short Answer: 20 marks
- Long Answer: 36 marks
- Numerical: 16 marks
- Case Study: 8 marks
- True/False: 6 marks
- **TOTAL: 106 marks** (or normalize to 100)

## DIFFICULTY PROGRESSION
- **Easy**: True/False, K-NN steps, basic MCQ
- **Medium**: Linear regression, correlation, classification metrics
- **Hard**: Tree building, Random Forest vs Bagging, complex numerical problems

---

# 7. FINAL EXAM TIPS

## Do's ✓
- Read all questions before starting
- Show all calculations (partial credit)
- Draw diagrams (trees, curves) clearly
- Define terms before using
- Check units & reasonableness
- Manage time: ~2 min per mark

## Don'ts ✗
- Skip hard questions initially (come back later)
- Forget to interpret results
- Confuse similar concepts (e.g., SD vs SE)
- Ignore real-world context (business reason)
- Make assumptions without stating
- Leave blanks (write something!)

## Last-Minute Review
1. Formulas written clearly
2. Interpretation practice
3. Common mistakes list (above)
4. Real-world examples
5. Algorithm flowcharts

---

**Good luck with your exam! You've got this! 💪**
