# Physical Inactivity and Happiness: A Cross-Country Machine Learning Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bodhi584/physical-inactivity-happiness-ml/blob/main/notebooks/physical_inactivity_happiness_ml.ipynb)

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

Use Python 3.10 or 3.11. Install the dependencies:

```bash
pip install -r requirements.txt
```

From the repository root, launch the notebook:

```bash
jupyter notebook notebooks/physical_inactivity_happiness_ml.ipynb
```

The notebook automatically resolves the included `data/` directory whether Jupyter is launched from the repository root or from the `notebooks/` directory. In Google Colab, it prompts for the three CSV files when they are not already available. Saved outputs are included so the results can also be reviewed without rerunning every cell.

## Data Sources

- [WHO Global Status Report on Physical Activity 2022: Country Profiles](https://www.who.int/publications/i/item/9789240064119)
- [World Happiness Report 2015](https://worldhappiness.report/ed/2015/)
- [World Happiness Report data-sharing page](https://worldhappiness.report/data-sharing/) for the multi-year happiness index series

The repository retains the three analysis-ready CSV files for reproducibility. Rights in the source data remain with their respective providers, and reuse should follow the terms stated on the linked source pages.

## Limitations

- The analysis is observational and cross-country, so model associations should not be interpreted as causal effects.
- The principal happiness and physical-activity sources refer to different years (2015 and 2022), making the comparison exploratory rather than a same-year panel analysis.
- Missing physical-inactivity values are mean-imputed in the preprocessing pipeline; this supports a complete modeling sample but may reduce country-level variation.

## Skills Demonstrated

- Data cleaning and feature preparation
- Regression analysis and model comparison
- Cross-validation and hyperparameter tuning
- Tree-based ensemble models
- SHAP model explainability
- K-Means clustering
- PCA dimensionality reduction
- Reproducible notebook-based reporting
