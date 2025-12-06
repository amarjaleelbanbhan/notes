# ⚡ QUICK REFERENCE CHEAT SHEET
## Last-Minute Exam Survival Guide

---

## 🎯 DATA TYPES AT A GLANCE

### Numeric
- **Continuous**: Height, temperature, time (any value)
- **Discrete**: Clicks, counts, integers (specific values)

### Categorical
- **Nominal**: No order (colors, countries)
- **Ordinal**: Ranked (ratings, education level)
- **Binary**: Two values (yes/no, true/false)

---

## 📊 STATISTICS QUICK FACTS

### Location (Center)
- **Mean**: Average, sensitive to outliers
- **Median**: Middle value, robust
- **Trimmed Mean**: Remove extremes, middle ground

### Spread (Variability)
- **Variance/SD**: Around mean, sensitive outliers
- **IQR**: Q3 - Q1, robust
- **Percentile**: % of data below this

### Formulas
- **SD = √(Σ(x-mean)²/n)**
- **IQR = Q3 - Q1**
- **SE = SD/√n** (smaller = more precise)

---

## 🔗 CORRELATION QUICK REFERENCE

**Pearson's r**: -1 to +1
- **+1**: Perfect positive (both increase)
- **0**: No linear relationship
- **-1**: Perfect negative (opposite directions)
- **0.5 to 1 or -1 to -0.5**: Strong
- **0 to 0.3**: Weak

**Key**: Correlation ≠ Causation!

---

## 📈 SAMPLING CONCEPTS

| Concept | Meaning |
|---|---|
| **Random Sampling** | Each element equal chance (unbiased) |
| **Bias** | Systematic error in one direction |
| **Selection Bias** | Data collection skewed |
| **Regression to Mean** | Extremes followed by averages |

---

## 🔔 DISTRIBUTIONS CHEAT SHEET

| Distribution | Used For | Key Fact |
|---|---|---|
| **Normal** | General, baseline | Bell curve, mean=median |
| **t-Distribution** | Small samples | Fatter tails than normal |
| **Binomial** | Success/fail | Fixed trials, 2 outcomes |
| **Chi-Square** | Categorical | Testing independence |
| **F-Distribution** | Comparing variances | Always positive |
| **Poisson** | Event counts | Mean = Variance = λ |

---

## ⭐ CENTRAL LIMIT THEOREM (CLT)

**The Magic**: Sample means ≈ normal distribution
- Works even if population skewed!
- Bigger samples → better approximation
- SE = σ/√n (larger n → smaller SE)

**Use**: Confidence intervals without knowing population distribution

---

## 🎲 CONFIDENCE INTERVALS

**Formula**: X̄ ± (z × SE)

| Level | z-value |
|---|---|
| 90% | 1.645 |
| 95% | 1.96 |
| 99% | 2.58 |

**Interpretation**: NOT 95% chance value in interval, but 95% of such intervals contain true value!

---

## 🔄 BOOTSTRAP IN 3 STEPS

1. Resample original data WITH replacement (many times)
2. Calculate statistic (mean, median) for each resample
3. Distribution of statistics ≈ sampling distribution

**Why**: Works without assuming distribution, handles skewed data

---

## 🤖 MACHINE LEARNING TYPES

### Supervised (Labeled Data)
- **Classification**: Predict categories
  - Binary: 2 classes
  - Multi-class: 3+ classes
  - Multi-label: Multiple per item
- **Regression**: Predict numbers

### Unsupervised (No Labels)
- **Clustering**: Group similar items

### Semi-Supervised
- Mix of labeled + unlabeled

### Reinforcement
- Learn from rewards/penalties

---

## 📐 LINEAR REGRESSION

**Equation**: Y = mX + b

| Symbol | Meaning |
|---|---|
| **m** | Slope (change in Y per unit X) |
| **b** | Y-intercept (Y when X=0) |
| **mX+b** | Predicted value |
| **Actual - Predicted** | Residual/Error |

**Cost Function**: MSE = (1/2m)Σ(predicted-actual)²

**R²**: % of variance explained (0 to 1, higher better)

---

## 🎯 LOGISTIC REGRESSION

**Output**: Probability [0-1]

**Function**: Sigmoid σ(z) = 1/(1+e^(-z))

**Decision**: P ≥ 0.5 → Class 1, else Class 0

**Key Difference**: Predicts probability, not continuous value!

**Cost**: Log Loss = -(1/m)Σ[y×log(ŷ) + (1-y)×log(1-ŷ)]

---

## 👥 K-NEAREST NEIGHBORS (KNN)

**Process**:
1. Choose k
2. Find k nearest points
3. Vote (classification) or average (regression)

**Distance Metrics**:
- **Euclidean**: d = √[(x₁-x₂)² + (y₁-y₂)²]
- **Manhattan**: d = |x₁-x₂| + |y₁-y₂|

**Preprocessing**: Normalize (z-score), encode categorical (one-hot)

**k Choice**:
- Small k: Overfitting
- Large k: Underfitting
- Sweet spot: Cross-validation

---

## 🌳 DECISION TREES

**Split**: Minimize impurity

**Impurity Measures**:
- **Entropy**: 0 (pure) to 1 (50-50 mix)
- **Gini**: 0 (pure) to 0.5 (50-50 mix)

**Information Gain**: Reduction in impurity after split

**Stopping Rules**:
- Min samples per leaf
- Max depth
- Min information gain

**Regression**: Predict mean of values in leaf

---

## 🌲 RANDOM FOREST

**Formula**: Bagging + Random Feature Selection

**Process**:
1. Bootstrap samples
2. Each tree: Random feature subset at each split
3. Aggregate (vote/average)

**vs Bagging**:
- RF: More diverse trees
- RF: Usually better accuracy
- Bagging: Simpler to understand

---

## 🧠 NAÏVE BAYES

**Core**: Bayes' Theorem = P(y|X) = P(X|y)×P(y)/P(X)

**Assumption**: Features conditionally independent (naive, but works!)

**Types**:
- **Gaussian**: Continuous data
- **Multinomial**: Word counts (text)
- **Bernoulli**: Binary features (word present/absent)

---

## ✅ CLASSIFICATION METRICS

**Confusion Matrix**:
```
         Predicted
         Pos  Neg
Actual Pos [TP][FN]
       Neg [FP][TN]
```

| Metric | Formula | Meaning |
|---|---|---|
| **Accuracy** | (TP+TN)/Total | % correct (misleading if imbalanced!) |
| **Precision** | TP/(TP+FP) | Of predicted positives, % correct |
| **Recall** | TP/(TP+FN) | Of actual positives, % caught |
| **F1** | 2×P×R/(P+R) | Balanced (use for imbalanced) |

---

## 🎪 COMMON MISTAKES TO AVOID

1. **SD vs SE**: SD spreads data, SE spreads mean (SE = SD/√n)
2. **Correlation = Causation**: FALSE! Can move together without causation
3. **CI Interpretation**: NOT 95% chance value in interval
4. **Accuracy with Imbalance**: Misleading! Use Precision/Recall/F1
5. **Overfitting**: High train acc, low test acc
6. **Underfitting**: High both errors

---

## 🧮 MUST-KNOW FORMULAS

```
Slope: m = Σ(x-x̄)(y-ȳ) / Σ(x-x̄)²
Intercept: b = ȳ - m×x̄
MSE: (1/2m)Σ(predicted-actual)²
SE: SD/√n
Correlation: r = Σ(x-x̄)(y-ȳ) / √[Σ(x-x̄)²×Σ(y-ȳ)²]
CI: X̄ ± z×SE
IG: H(parent) - Σ(p×H(child))
Gini: 1 - Σ(pᵢ²)
Precision: TP/(TP+FP)
Recall: TP/(TP+FN)
F1: 2×P×R/(P+R)
Sigmoid: σ(z) = 1/(1+e^(-z))
Bayes: P(y|X) = P(X|y)×P(y)/P(X)
Euclidean: d = √[Σ(xᵢ-yᵢ)²]
z-score: z = (x-mean)/SD
```

---

## ⚡ EXAM STRATEGY

**Time Management**
- ~2 min per mark
- Easy questions first
- Hardest last (if time permits)

**Answering Tips**
- Define terms before using
- Show all work (partial credit)
- Interpret results (don't just calculate)
- Check reasonableness
- Draw diagrams clearly

**What to Memorize**
- Formula list (above)
- Algorithm steps
- Metric interpretations
- Real-world applications

**What to Understand**
- WHY algorithms work
- When to use which
- Pros/cons of each
- Business context

---

## 📋 CONCEPT QUICK CHECK (If unsure, review)

- [ ] Data types (numeric, categorical, nominal, ordinal, binary)
- [ ] Location vs Variability
- [ ] SD vs SE
- [ ] Correlation (range -1 to 1)
- [ ] Sampling bias & random sampling
- [ ] CLT & why important
- [ ] Bootstrap process
- [ ] Confidence interval interpretation
- [ ] ML types (supervised, unsupervised, semi-supervised)
- [ ] Linear regression (slope, intercept, MSE)
- [ ] Logistic regression (sigmoid, probability output)
- [ ] K-NN (process, k choice, distance metrics)
- [ ] Decision trees (splits, impurity, overfitting)
- [ ] Random Forest (bootstrap + random features)
- [ ] Naïve Bayes (Bayes' theorem, conditional independence)
- [ ] Precision vs Recall vs F1
- [ ] Overfitting vs Underfitting

---

## 🎯 HIGH-PROBABILITY EXAM QUESTIONS

1. **Calculate correlation** → Use formula, interpret
2. **Build decision tree** → Show splits, entropy/gini calculations
3. **Precision vs Recall** → Define both, business context
4. **Linear regression** → Calculate slope & intercept
5. **Confidence interval** → Calculate, interpret correctly
6. **K-NN algorithm** → Steps + preprocessing + k choice
7. **Logistic vs Linear** → Key differences
8. **Random Forest vs Bagging** → Compare
9. **Classification metrics** → Confusion matrix, which metric when
10. **Bootstrap explanation** → Why useful, how it works

---

**✨ Remember: SHOW YOUR WORK. Good luck! 💪**
