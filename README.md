# Cryptocurrencies

## Overview of Project
We understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce our dimensions, and how to reduce the principal components using PCA.
It’s time to put all these skills to use by creating an analysis for our clients who are preparing to get into the cryptocurrency market.The data Martha will be working with is not ideal,
so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. 
To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

### Deliverables:
This new assignment consists of three technical analysis deliverables and a written report.

1. ***Deliverable 1:*** Preprocessing the Data for PCA
2. ***Deliverable 2:*** Reducing Data Dimensions Using PCA
3. ***Deliverable 3:*** Clustering Cryptocurrencies Using K-means
4. ***Deliverable 4:*** Visualizing Cryptocurrencies Results


## Resources:

* Data Source: `crypto_data.csv`
* Data Tools:  `crypto_clustering_starter_code.ipynb`.
* Software: `Python 3.7`, `Anaconda 4.8.5`, `Jupyter Notebook 6.1.4` and `Pandas`

## Results

# Deliverable 1:  
## Preprocessing the Data for PCA

1. Read in the `crypto_data.csv` to the Pandas DataFrame named `crypto_df`.
2. Kept all the cryptocurrencies that are being traded.
3. Kept all the cryptocurrencies that have a working algorithm.
4. Dropped the `IsTrading` column.
5. Removed rows that have at least one null value.
6. Filtered the `crypto_df` DataFrame so it only has rows where coins have been mined.
7. Created a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
8. Removed the `CoinName` column from the `crypto_df` DataFrame since it's not going to be used on the clustering algorithm.

![crypto-df.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/crypto-df.PNG?raw=true)

9. Used the `get_dummies()` method to create variables for the two text features, `Algorithm` and `ProofType`, and store the resulting data in a new DataFrame named `X`.
10. Used the StandardScaler `fit_transform()` function to standardize the features from the `X` DataFrame.

![get_dummies_std.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/get_dummies_std.PNG?raw=true)


# Deliverable 2:  
## Reducing Data Dimensions Using PCA 

The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components. 
Created a new DataFrame named `pcs_df` that includes the following columns, `PC 1`, `PC 2`, and `PC 3`, and uses the index of the `crypto_df` DataFrame as the index.


![pcs_df.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/pcs_df.PNG?raw=true)


# Deliverable 3:  
## Clustering Cryptocurrencies Using K-means 


Using our knowledge of the K-means algorithm,we have created an elbow curve using `hvPlot` to find the best value for K from the `pcs_df` DataFrame created in Deliverable 2.
 Then, ran the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.

    
    - An elbow curve is created using `hvPlot` to find the best value for K 
	
![elbow-curve.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/elbow-curve.PNG?raw=true)

    - Predictions are made on the K clusters of the cryptocurrencies’ data 
	
![predictions.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/predictions.PNG?raw=true)

    - A new DataFrame is created with the same index as the `crypto_df` DataFrame and has the following columns: `Algorithm`, `ProofType`, `TotalCoinsMined`, `TotalCoinSupply`, `PC 1`, `PC 2`, `PC 3`, `CoinName`, and `Class` 
	
![clustered_df.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/clustered_df.PNG?raw=true)



# Deliverable 4:  
## Visualizing Cryptocurrencies Results 

Using your knowledge of creating scatter plots with Plotly Express and `hvplot`, you’ll visualize the distinct groups that correspond to the three principal components you created in 
Deliverable 2, then you’ll create a table with all the currently tradable cryptocurrencies using the `hvplot.table()` function.


 - The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover
	
	![scatter-plot.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/scatter-plot.PNG?raw=true)

- A table with tradable cryptocurrencies is created using the hvplot.table() function
		
	![table.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/table.PNG?raw=true)
	
- The total number of tradable cryptocurrencies is printed
	
	![total.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/total.PNG?raw=true)

- A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns

	![D4-1.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/D4-1.PNG?raw=true)

* A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point

	![scatter-plot2.PNG](https://github.com/Praveeja-Sasidharan-Suni/Cryptocurrencies/blob/main/Images/scatter-plot2.PNG?raw=true)
	
## Summary
	Using Unsupervised learning,Preprocessing the Data for PCA, Reducing Data Dimensions Using PCA,Clustering Cryptocurrencies Using K-means,Visualizing Cryptocurrencies Results are done successfully.




