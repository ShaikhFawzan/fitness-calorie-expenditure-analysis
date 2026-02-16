# Exercise Performance and Calorie Expenditure Analysis

**Author:** Fawzan Shaikh

## Project Overview

This project investigates the physiological drivers of caloric expenditure during exercise, moving beyond oversimplified categorical labels to identify what truly impacts energy burn during workouts. Using statistical analysis and predictive modeling on 973 gym member sessions, the analysis reveals actionable insights for optimizing workout efficiency.

### Key Finding
**Session volume and consistency are significantly stronger predictors of calorie burn than workout type or demographic categories.** The final regression model explains 96.1% of variance in calorie expenditure (R² = 0.961).

## Business Question

What are the primary drivers of calorie expenditure during workout sessions, and how much predictive power do intensity metrics have compared to categorical labels like gender or workout type?

## Dataset

- **Source:** [Gym Members Exercise Dataset (Kaggle)](https://www.kaggle.com/datasets/valakhorasani/gym-members-exercise-dataset)
- **Size:** 973 samples
- **Features:** Age, Gender, Weight, Height, Heart Rate metrics (Max/Avg/Resting BPM), Session Duration, Workout Type, Body Fat %, Water Intake, Workout Frequency, Experience Level, BMI

## Methodology

### 1. Exploratory Data Analysis (EDA)
- Comprehensive feature correlation analysis with caloric expenditure
- Distribution analysis and outlier detection
- Visual exploration of relationships between variables

### 2. Statistical Inference
- **One-Way ANOVA** to test whether workout type categories (Cardio, HIIT, Strength, Yoga) have statistically significant differences in calorie burn
- Hypothesis testing to validate categorical predictor relevance

### 3. Predictive Modeling
- **Multiple Linear Regression (OLS)** to quantify the impact of physiological and behavioral variables
- Feature selection through statistical significance testing
- Model refinement to reduce multicollinearity and improve interpretability

## Key Results

### Regression Model Performance
- **R² = 0.961** (96.1% variance explained)
- **Model Significance:** p < 0.001
- All continuous predictors statistically significant at α = 0.05

### Primary Drivers of Calorie Burn

| Feature | Coefficient | Impact |
|---------|-------------|--------|
| **Session Duration** | +677 cal/hour | Strongest predictor by far |
| **Body Fat %** | -5.06 cal/% | Higher fat % = lower burn |
| **Workout Frequency** | -9.02 cal/day | Negative relationship (likely due to shorter session durations) |
| **Avg Heart Rate** | +6.27 cal/BPM | Intensity metric |
| **Age** | -3.33 cal/year | Negative relationship |

### Workout Type: Not Statistically Significant
After controlling for duration, heart rate, and body composition, **workout type (HIIT, Strength, Yoga vs. Cardio) showed no statistically significant difference** in calories burned. This suggests that *how long* and *how intensely* one exercises matters more than the specific workout label.

## Actionable Insights

1. **Prioritize session volume** over chasing specific "high-burn" workout categories
2. **Workout type doesn't matter as much as you think** - HIIT, Strength, Yoga, and Cardio show no statistically significant differences once intensity and duration are controlled for
3. **Quality over frequency** - More frequent workouts show a negative relationship with per-session calorie burn, suggesting that frequent exercisers may perform shorter/less intense sessions
4. **Body composition matters** - Individuals with lower body fat % (more lean muscle mass) burn significantly more calories during the same workout



## Technical Skills Demonstrated

- **Python Libraries:** pandas, matplotlib, seaborn, scipy.stats, statsmodels
- **Statistical Methods:** One-Way ANOVA, OLS Multiple Linear Regression, hypothesis testing
- **Data Analysis:** Feature engineering, correlation analysis, multicollinearity assessment
- **Data Visualization:** Distribution plots, correlation heatmaps, regression diagnostics
- **Model Interpretation:** Coefficient analysis, p-value interpretation, R² evaluation

## Project Structure

```
fitness-analysis/
│
├── Data/
│   └── gym_members_exercise_tracking.csv
├── Fitness_Analysis.ipynb    # Main analysis notebook
├── Requirements/
│   └── Requirements.txt
└── README.md
```

## Requirements

```python
pandas
matplotlib
seaborn
scipy
statsmodels
jupyter
```

## How to Run
**Note:** You can view the analysis directly on GitHub by clicking on `Fitness_Analysis.ipynb` - no installation required!

To run the notebook locally:
1. Clone this repository
```
git clone https://github.com/ShaikhFawzan/fitness-calorie-expenditure-analysis.git
cd fitness-calorie-expenditure-analysis
```

2. Install dependencies
```
pip install -r Requirements/Requirements.txt
```

3. Launch Jupyter Notebook
```
jupyter notebook Fitness_Analysis.ipynb
```

## References

Dataset: [Gym Members Exercise Dataset](https://www.kaggle.com/datasets/valakhorasani/gym-members-exercise-dataset)

---

*This project was developed to demonstrate data analysis and statistical modeling skills for data science/analyst positions.*
