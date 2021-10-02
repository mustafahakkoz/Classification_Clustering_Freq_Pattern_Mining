# Classification_Clustering_Freq_Pattern_Mining

2019-2020 Fall CSE4063 - Data Mining

3 projects covering **Classification**, **Clıustering Analysis** and **Frequent Pattern Mining** in the scope of Data Mining lectures in Marmara University. Notebooks are written on Kaggle platform so online versions of them are suggested for better visuals.

---

#### Online Notebooks:

1. [Phishing Websites | Kaggle](https://www.kaggle.com/hakkoz/phishing-websites)

2. [Absenteeism at Work - Clustering | Kaggle](https://www.kaggle.com/hakkoz/absenteeism-at-work-clustering)

3. [Frequent Pattern Miningv2 | Kaggle](https://www.kaggle.com/hakkoz/frequent-pattern-miningv2)

---

#### Repo Content and Implementation Steps:

[**phishing-websites.ipynb**]()

- 6 classifiers; **CART**, **C4.5**, **Naive-Bayes**, **Support Vector Machine**, **Neural Network with 1 hidden layer** and **Neural Network with 2 hidden layers** are trained on [Phishing Websites](http://archive.ics.uci.edu/ml/datasets/Phishing+Websites) dataset. Hyperparameter tuning is implemented in 5-fold cross-validation with necesarry preprocessing steps.

[**absenteeism-at-work-clustering.ipynb**]()

- Clustering Analysis on [Absenteeism at Work Dataset](https://archive.ics.uci.edu/ml/datasets/Absenteeism+at+work) is implemented. First EDA, outlier detection (IQR), normalization (Min-Max Scaler) and feature selection with Random Forest (and Permutation Importance) are completed.

- **K-means** clusters are visaulized by 3D t-SNE plots after searching for possible elbow points (based on **inertia** attribute). After that **PCA+K-means** pipeline is tested. Most of valuable information about data is lost with PCA so, resulting graphs seem incomplete. Using k-means on original 7-dimensional data then plotting with t-SNE gives better results. 

- There's no **inertia** (Sum of squared distances of samples to their closest cluster center) attribute of **AgglomerativeClustering** class so we used **silhouette coefficient** (best:1, worst:-1) to select cluster number of **AGNES**. Again 3D t-SNE clusters and **dendogram** is plotted.

- **DBSCAN** model is also implemented and best values for the parameters **eps** and **min_samples** are found in gridsearch manner with **silhouette coefficient**. Again best model is visaulized in 3D t-SNE **plot.ly** graphs.

- And finally in evaluation step, best of 3 models are compared by using 9 metrics:
  
  - Estimated number of clusters
  - Estimated number of noise points
  - Homogeneity
  - Completeness
  - V-measure
  - Adjusted Rand Index
  - Adjusted Mutual Information
  - Fowlkes-Mallows score
  - Silhouette Coefficient
  
  Explanations and comments on the results can be found in notebooks.

[**frequent-pattern-miningv2.ipynb**]()

- Association rules for a given dataset is extracted by using **Aprori**, **FP-Growth** and **ECLAT** algorithms of **mlxtend** library after preprocessing with **TransactionEncoder**. Models are compared with memory usages and runtimes.




