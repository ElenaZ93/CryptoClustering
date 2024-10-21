# Crypto Clustering Challenge

## Overview
In this challenge, we aim to utilize Python and unsupervised learning techniques to explore whether cryptocurrencies are influenced by 24-hour or 7-day price changes. Specifically, we'll apply the K-means clustering algorithm to group cryptocurrencies based on price change percentages, and we'll further optimize the clustering process using Principal Component Analysis (PCA).

This repository contains the steps, code, and visualizations necessary to understand the clustering behavior of cryptocurrencies over specific time periods.

## Instructions

### 1. Setup and Data Loading
- The notebook file has been renamed from `Crypto_Clustering_starter_code.ipynb` to `Crypto_Clustering.ipynb`.
- Load the `crypto_market_data.csv` file into a DataFrame.
- Review the summary statistics and plot the data to gain initial insights before moving forward.

### 2. Data Preparation
- **Standardize the Data:** Normalize the data using the `StandardScaler()` module from scikit-learn.
- **Re-indexing:** Create a new DataFrame with the scaled data, and set the `coin_id` index from the original DataFrame as the index for the new scaled DataFrame.

### 3. K-Means Clustering

#### A. **Finding the Optimal Value for k**
- Use the elbow method to identify the best value for `k`:
    1. Create a range of `k` values from 1 to 11.
    2. Compute the inertia values for each `k` in a loop.
    3. Plot an elbow curve to visually determine the optimal value of `k`.
- Answer the following question: *What is the best value for `k`?*

#### B. **Clustering the Cryptocurrencies**
- Apply K-means clustering using the scaled DataFrame for the best value of `k`.
- Add a new column to the DataFrame to store the predicted clusters.
- Create a scatter plot with the following:
    - X-axis: `price_change_percentage_24h`
    - Y-axis: `price_change_percentage_7d`
    - Color the points by the cluster labels.
    - Use the `coin_id` column in the `hover_cols` parameter to display additional information on hover.

### 4. PCA (Principal Component Analysis) for Dimensionality Reduction

#### A. **Perform PCA**
- Apply PCA to the scaled data and reduce the features to 3 principal components.
- Retrieve the explained variance to understand how much information each component holds.
- Answer the following question: *What is the total explained variance of the three principal components?*

#### B. **K-Means with PCA Data**
- Apply the elbow method on the PCA DataFrame to find the best `k`.
- Answer the following questions:
    - *What is the best value for `k` when using the scaled PCA DataFrame?*
    - *How does this differ from the best `k` value using the original scaled DataFrame?*

#### C. **Cluster Cryptocurrencies Using PCA Data**
- Cluster the cryptocurrencies using the PCA-transformed data.
- Add a new column for the predicted clusters.
- Create a scatter plot with the following:
    - X-axis: `PC1`
    - Y-axis: `PC2`
    - Color the points by the cluster labels.
    - Use the `coin_id` column in the `hover_cols` parameter to display additional information on hover.

### 5. Analysis and Insights
- Evaluate the impact of reducing the dataset's features using PCA.
- Compare the clustering results with and without PCA.
- Answer the question: *What is the impact of using fewer features for clustering?*

### 6. Additional Resources
- For guidance on creating composite plots, check the [Composing Plots documentation](https://holoviz.org/tutorial/Composing_Plots.html) in hvPlot.

---

## Technologies Used
- Python
- scikit-learn
- Pandas
- hvPlot
- Principal Component Analysis (PCA)
- K-means Clustering

## Conclusion
Through this challenge, you'll gain a deeper understanding of how to cluster data with unsupervised learning techniques, optimize the clustering with PCA, and visually analyze cryptocurrency behavior through clustering methods.

Feel free to explore the code, experiment with the data, and build on this project to further improve your knowledge of machine learning and cryptocurrency market analysis.

---

## License
This repository is licensed under the MIT License.
