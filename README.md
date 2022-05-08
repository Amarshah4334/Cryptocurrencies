# Cryptocurrencies
Unsupervised Machine Learning and Cryptocurrencies
You and Martha have done your research. You understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. It’s time to put all these skills to use by creating an analysis for your clients who are preparing to get into the cryptocurrency market.

Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

#

### Data: crypto_data.csv, crypto_clustering_starter_code.ipynb.
### Tools: Python, Visual Studio Code, Anaconda, Scikit-learn, plotly, hvplot, Jupyter Notebook and Pandas
### Environment: Machine Learning

# Deliverables

This new assignment consists of four technical analysis deliverables. You will submit the following:

## Deliverable 1: Preprocessing the Data for PCA
## Deliverable 2: Reducing Data Dimensions Using PCA
## Deliverable 3: Clustering Cryptocurrencies Using K-means
## Deliverable 4: Visualizing Cryptocurrencies Results

# Deliverable 1: Preprocessing the Data for PCA


•	The crypto_data.csv was retrieved from CryptoCompare 
•	Keep all the cryptocurrencies that are being traded.
•	Drop the IsTrading column.
•	Remove rows that have at least one null value.
•	Filter the crypto_df DataFrame so it only has rows where coins have been mined.
•	Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
•	Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.
•	Use the get_dummies() method to create variables for the two text features, Algorithm and ProofType, and store the resulting data in a new DataFrame named X.
•	Use the StandardScaler fit_transform() function to standardize the features from the X DataFrame.


![image](https://user-images.githubusercontent.com/96351897/167318942-cc525d60-6c57-4f24-924a-6ffb7fa0257d.png)


# Deliverable 2: Reducing Data Dimensions Using PCA

•	Continue using the crypto_clustering.ipynb file from Deliverable 1 where you’ve already performed the preprocessing steps.
•	Using the information we’ve provided, apply PCA to reduce the dimensions to three principal components.
•	Create a new DataFrame named pcs_df that includes the following columns, PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.


![image](https://user-images.githubusercontent.com/96351897/167318988-c91d42d2-a774-4e9d-8222-3034e712a277.png)




# Deliverable 3: Clustering Cryptocurrencies Using K-means

•	Continue using the crypto_clustering.ipynb file that you used in Deliverable 2 to reduce the dataset to three dimensions.
•	Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K.
•	Next, use the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.
•	Create a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns. The index should be the same as the crypto_df DataFrame.
•	Add the CoinName column that holds the names of the cryptocurrencies, which you created in Step 7 of Deliverable 1, to the clustered_df.
•	Add another new column to the clustered_df named Class that holds the predictions, i.e., model.labels_, from Step 3.


![image](https://user-images.githubusercontent.com/96351897/167319005-298ca779-2b1b-4a07-844d-216dc38beb17.png)


# Deliverable 4: Visualizing Cryptocurrencies Results


•	Continue using the crypto_clustering.ipynb file from Deliverable 3 where you have predicted the K clusters for the cryptocurrencies’ data.
•	Create a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.
•	Add the CoinName and Algorithm columns to the hover_name and hover_data parameters, respectively, so each data point shows the CoinName and Algorithm on hover.
•	Create a table with tradable cryptocurrencies using the hvplot.table() function.


![image](https://user-images.githubusercontent.com/96351897/167319052-1376848e-9ebc-4d89-bc34-a33e1ebceb23.png)


•	Print the total number of tradable cryptocurrencies in the clustered_df DataFrame.
•	Use the MinMaxScaler().fit_transform method to scale the TotalCoinSupply and TotalCoinsMined columns between the given range of zero and one.
•	Create a new DataFrame using the clustered_df DataFrame index that contains the scaled data you created in Step 5.
•	Add the CoinName column from the clustered_df DataFrame to the new DataFrame.
•	Add the Class column from the clustered_df DataFrame to the new DataFrame.


![image](https://user-images.githubusercontent.com/96351897/167319079-5b9dd5bb-ce48-40d9-842f-dac7584eabe0.png)


•	Create an hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class", and have it show the CoinName when you hover over the the data point.


![image](https://user-images.githubusercontent.com/96351897/167319091-7c3bd5ac-b89d-4ed1-8b0b-f92612494d0b.png)



