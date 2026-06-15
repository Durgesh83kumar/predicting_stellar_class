# V1 - CatBoost Baseline

Model:
CatBoostClassifier(
    iterations=500,
    learning_rate=0.1,
    depth=6
)

Features:
alpha, delta, u, g, r, i, z, redshift,
spectral_type, galaxy_population

Validation:
5-Fold Stratified CV

CV Score:
0.94744

Kaggle Public Score:
0.94779

Notes:
First successful submission.


# V2 - Tuned CatBoost

Parameters:
iterations=1000
depth=8
learning_rate=0.05

CV Score:
0.94979

LB Score:
0.95053

Improvement:
+0.00274