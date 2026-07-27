# Physical Inactivity and Happiness: A Cross-Country Machine Learning Analysis

This repository contains a reproducible notebook for a cross-country analysis of physical inactivity, national happiness, and broader well-being indicators.

The project uses regression models, ensemble learning, SHAP explainability, K-Means clustering, and PCA to examine why countries with higher physical inactivity can still appear happier at the national level when socioeconomic and health-related factors are considered.

## Portfolio Summary

This is an individual data science portfolio project. It is designed to show an end-to-end workflow: framing a real-world analytical question, preparing multi-source public datasets, comparing statistical and machine learning models, interpreting model outputs, and packaging the work in a reproducible notebook.

![Model performance comparison](figures/model_performance.png)

## Project Highlights

- Combined WHO physical activity data with World Happiness indicators.
- Compared simple regression, multiple OLS, Random Forest, and Gradient Boosting models.
- Used SHAP values to evaluate the relative contribution of each feature.
- Applied K-Means clustering and PCA to describe country-level development profiles.
- Kept the notebook reproducible with local datasets included in the `data/` folder.

## Main Results

The final notebook reports the following model and dimensionality-reduction results:

- Simple Linear Regression test R-squared: `0.3093`
- Multiple OLS test R-squared: `0.8292`
- Tuned Random Forest test R-squared: `0.8763`
- Multiple OLS cross-validation R-squared: `0.807`
- Multiple OLS adjusted R-squared: `0.7950`
- PCA variance explained by PC1 and PC2: `77.5%`
- PCA variance explained by PC1 to PC3: `88.0%`

SHAP feature contribution in the final Random Forest model:

![SHAP feature contribution](figures/shap_contribution.png)

| Feature | Contribution |
| --- | ---: |
| GDP per Capita | 36.4% |
| Healthy Life Expectancy | 32.4% |
| Social Support | 14.9% |
| Freedom | 13.6% |
| Physical Inactivity | 2.8% |

These results should be interpreted as model-based associations, not causal estimates. The notebook includes a DAG-based discussion to clarify why GDP-related confounding is important in this topic.

![PCA explained variance](figures/pca_explained_variance.png)

## Repository Structure

```text
.
├── data/
│   ├── who_physical_activity.csv
│   ├── world_happiness.csv
│   └── world_happiness_allyears.csv
├── figures/
│   ├── model_performance.png
│   ├── pca_explained_variance.png
│   └── shap_contribution.png
├── notebooks/
│   └── physical_inactivity_happiness_ml.ipynb
├── requirements.txt
└── README.md
```

## How to Run

Install the dependencies:

```bash
pip install -r requirements.txt
```

Then open and run:

```text
notebooks/physical_inactivity_happiness_ml.ipynb
```

The notebook is designed to run from the repository root. It also contains saved outputs so the results can be reviewed without rerunning every cell.

## Skills Demonstrated

- Data cleaning and feature preparation
- Regression analysis and model comparison
- Cross-validation and hyperparameter tuning
- Tree-based ensemble models
- SHAP model explainability
- K-Means clustering
- PCA dimensionality reduction
- Reproducible notebook-based reporting

## Data Note

The datasets are included so this individual portfolio project can be reproduced. Anyone reusing the data should check the original source terms from WHO and the World Happiness data providers.
