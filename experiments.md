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

# V3 - Feature Engineering

New Features:
u_g = u - g
g_r = g - r
r_i = r - i
i_z = i - z

Model:
CatBoost
iterations=1000
depth=8
learning_rate=0.05

CV Score:
0.95047

LB Score:
0.95153

Improvement:
+0.00100

# V4 - Extended Color Indices

Added:
u_r
g_i
r_z

CV Score:
0.95106

LB Score:
0.95211

# V5

Removed:
- spectral_type
- galaxy_population

Features:
- alpha
- delta
- u
- g
- r
- i
- z
- redshift
- u_g
- g_r
- r_i
- i_z
- u_r
- g_i
- r_z

Model:
CatBoost
iterations=1000
depth=8
learning_rate=0.05

CV Score:
0.95120

LB Score:
0.95233

Best Model So Far


# V6 - LightGBM

Features:
- alpha
- delta
- u
- g
- r
- i
- z
- redshift
- u_g
- g_r
- r_i
- i_z
- u_r
- g_i
- r_z

Removed:
- spectral_type
- galaxy_population

Model:
LightGBM

Parameters:
n_estimators=1000
learning_rate=0.05
max_depth=8

CV Score:
0.95433

LB Score:
0.95545

Best Model So Far

# V7

Model: LightGBM

Feature Importance Findings:
- alpha, delta, redshift dominate
- engineered color indices are highly useful
- no obviously removable features

Params:
n_estimators=1500
learning_rate=0.03

CV:
0.95532

LB:
0.95524

Result:
CV improved but LB worsened.
Rejected.