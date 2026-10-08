## Refined Question: 
**How can K-Means and GMM clustering be used to identify distinct customer segments based on age, income, spending behavior, purchase frequency, and online engagement to support targeted marketing strategies?**

## Dataset Describtion:
Features: The dataset has 29 columns, including demographic information, product spending, purchase channels, and marketing campaign responses. Seven selected features will be used for clustering.

Target: No predefined target variable because customer segmentation uses unsupervised learning. The Response column will not be used as a clustering target.

Size: 2,240 customer records and 29 columns, with 2,240 unique customer IDs.

Limitations: There are 24 missing income values, extreme values in birth year and income, no existing customer segment labels, and historical customer records from 2012–2014.

## Data cleaning plan: 
1/Load the dataset using pandas and check for missing values and data types.

2/Remove the missing values

3/Convert Dt_Customer into datetime format.

4/Select the seven numerical features needed for clustering and exclude irrelevant columns.

## Feature engineering plan

Age: Calculate customer age using 2026 - Year_Birth.

Total_children: Combine Kidhome and Teenhome.

Total_spend: Calculate total spending across six product categories.

Customer_since: Calculate the number of days since customer enrollment.

Feature Scaling: Apply StandardScaler to the seven selected clustering features.

PCA: Reduce the scaled data to two dimensions for visualizing customer clusters.

## Models and Why

K-Means Clustering: The main model used to group customers based on similar demographic and purchasing behavior. The Elbow Method examines 2–9 clusters, and the notebook uses 6 clusters for the final model.

Gaussian Mixture Model (GMM)	Groups customers using probability distributions and allows clusters to have different shapes and sizes.

## Evaluation Metrics and Why

Elbow Method (Inertia): Helps determine a suitable number of clusters by measuring within-cluster variation. Lower inertia indicates more compact clusters but generally decreases as cluster count increases.

Silhouette Score: Measures how well customers fit into their assigned clusters compared with other clusters. A higher score indicates better-defined clusters.

PCA Visualization: Displays customer clusters in two dimensions to help examine their separation visually.

