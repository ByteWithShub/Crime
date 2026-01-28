# Crime Pattern Analysis (Colab Notebook)

This repository contains the implementation of a comprehensive Machine Learning pipeline for analyzing crime incidents in the City of Ottawa. The project applies supervised, unsupervised, and anomaly detection techniques to uncover temporal, spatial, and behavioural crime patterns using real-world municipal data.

The analysis is implemented in a Google Colab / Jupyter Notebook and follows a full end-to-end workflow: data preprocessing, exploratory data analysis, feature engineering, classification, clustering, dimensionality reduction, and outlier detection.

### Project Overview
The project analyzes multi-year Ottawa crime incident data containing:
- Crime category and summaries
- Occurred and reported timestamps
- Neighbourhoods, sectors, and police divisions
- Geographic coordinates (x, y)

```
A complete ML pipeline is implemented:
- Data Processing & Feature Engineering
- Datetime parsing and cleaning\
- Hour extraction from HHMM format
- Time-of-day binning (Night / Morning / Afternoon / Evening)
- Weekend indicator creation
- Rare category consolidation
- Crime category mapping into: Person Crimes / Property Crimes / Society Crimes
- Numeric scaling and categorical encoding using ColumnTransformer
``` 

### Exploratory Data Analysis (EDA)
Includes:
- Crime group distributions
- Hourly and monthly crime trends
- Weekend vs weekday patterns
- Neighbourhood and sector analysis
- Heatmaps (Hour × Weekday)
- Ridgeline plots
- Sunburst visualizations
- Word clouds
- Time-series trends
_These reveal strong temporal rhythms, spatial hotspots, and behavioural patterns._

 
### Machine Learning Models:
```
Supervised Learning
Two classification models:
- Decision Tree (GridSearch tuned)
- Logistic Regression (Multinomial)

Evaluated across multiple train/test splits:
- 70/30
- 75/25
- 80/20
- 85/15

Metrics used:
- Accuracy
- Balanced Accuracy
- Precision / Recall / F1
- Macro F1
- Confusion matrices
Decision Trees captured nonlinear relationships more effectively, while Logistic Regression served as a linear baseline.


Dimensionality Reduction (PCA)
- Applied after preprocessing and encoding
- Used to reduce high-dimensional feature space
- Scree and cumulative variance plots generated
- 2D PCA used for visualization and clustering
- PCA highlights dominant temporal and spatial variance drivers.

Unsupervised Learning (KMeans)
Performed:

- Without PCA (numeric temporal + spatial features)
- With PCA (compressed feature space)
- Cluster quality evaluated using:
- Elbow method
- Silhouette scores
Clusters reveal natural behavioural groupings such as daytime vs nighttime crime patterns and neighbourhood-based separations.

Anomaly Detection
Isolation Forest applied on PCA-transformed data.
Multiple contamination levels tested
Final selection: 1% anomalies
Outliers analyzed by: Crime group, Time of day, Sector, Neighbourhood
This isolates rare and unusual crime incidents that deviate from typical patterns.
```

### Key Takeaway

_This project demonstrates how combining classification, clustering, PCA, and anomaly detection provides a multi-layered understanding of crime behaviour, supporting evidence-based public safety analytics and strategic planning._

