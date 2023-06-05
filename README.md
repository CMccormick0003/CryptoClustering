# CryptoClustering - An Exercise using Unsupervised Machine Learning

## Tools: Python, Scikit-learn

## Steps:
Source file crypto_market_data.csv was provided by Rutgers bootcamp instructors.
Load the crypto_market_data.csv into a DataFrame.
Get the summary statistics and plot the data to see what the data looks like before proceeding.
The summary statistics are visible in the Jupyter notebook.

### Original data in the dataframe (df_market_data):
![image](https://github.com/CMccormick0003/CryptoClustering/assets/120672518/939730b0-72e0-4bce-b831-00bc44487b90)

Prepare the Data
Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

### The first five rows of the scaled DataFrame
![image](https://github.com/CMccormick0003/CryptoClustering/assets/120672518/415722d0-5882-4a4c-960c-b8aabef07ab0)

## Find the Best Value for k Using the Original Scaled DataFrame
### Use the elbow method to find the best value for k using the following steps:

Create a list with the number of k values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

![image](https://github.com/CMccormick0003/CryptoClustering/assets/120672518/b353590f-a666-4874-a9a9-f8c0f981f6e6)

### What is the best value for k?
### The best  value for k is:  4

### Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

Initialize the K-means model with the best value for k.
Fit the K-means model using the original scaled DataFrame.
Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
Create a copy of the original data and add a new column with the predicted clusters.
Create a scatter plot using hvPlot as follows:
Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
Optimize Clusters with Principal Component Analysis

![image](https://github.com/CMccormick0003/CryptoClustering/assets/120672518/fcd7e0d8-04c1-48d6-a678-003676ba9fb1)


### Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.

Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:

### What is the total explained variance of the three principal components?
### The total explained variance is 37.19856 + 34.700813 + 17.603793. This is approximately equal to 89.5.

Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The first five rows of the PCA DataFrame
![image](https://github.com/CMccormick0003/CryptoClustering/assets/120672518/07fdb40d-3b98-4061-b9c3-20e5b14dca8f)

Find the Best Value for k Using the PCA Data
Use the elbow method on the PCA data to find the best value for k using the following steps:
Create a list with the number of k-values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the Elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
![image](https://github.com/CMccormick0003/CryptoClustering/assets/120672518/d19520c8-f83f-4371-ad63-3956ef2ef5b3)

### What is the best value for k when using the PCA data? 
### The best value for k when using the PCA data is:  4


### Does it differ from the best k value found using the original data?
### It does not differ from the best k found using the original data.


### Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

Initialize the K-means model with the best value for k.
Fit the K-means model using the PCA data.
Predict the clusters to group the cryptocurrencies using the PCA data.
Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
Create a scatter plot using hvPlot as follows:
Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

![image](https://github.com/CMccormick0003/CryptoClustering/assets/120672518/baafed9a-ceff-430b-9e64-01302d9b825e)

### What is the impact of using fewer features to cluster the data using K-Means?
### Even with fewer features, there were 4 identifiable clusters able to be seen. Therfore, the model with fewer features is as effective as the full model to predict cryptocurrency change percentages.
