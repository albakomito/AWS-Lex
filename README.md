# Unit_13_Assignment-Clustering Crypto

## Fetching Cryptocurrency Data (Ln 1-4)
In this section we: 
* Import the initial libraries from pandas and sklearn. (Ln 1)
* Use the https://min-api.cryptocompare.com/data/all/coinlist endpoint to fetch json data. (Ln 2) 
* Skip line 3: see line 4 (Ln 3). 
* Use the csv file provide and create our dataframe (Ln 4). 


## Data Preprocessing (Ln 5 -15)
In this section we: 
* Keep only necessary columns:'CoinName','Algorithm','IsTrading','ProofType','TotalCoinsMined','TotalCoinSupply' (Ln 5). 
* Keep only cryptocurrencies that are trading (Ln 6). 
* Keep only cryptocurrencies with a working algorithm (Ln 7). 
* Remove the "IsTrading" column (Ln 8). 
* Remove rows with at least 1 null value (Ln 9). 
* Remove rows with cryptocurrencies having no coins mined (Ln 10). 
* Drop rows where there are 'N/A' text values (Ln 11). 
* Store the 'CoinName'column in its own DataFrame prior to dropping it from crypto_df (Ln 12). 
* Drop the 'CoinName' column since it's not going to be used on the clustering algorithm (Ln 13). 
* Create dummy variables for text features (Ln 14). 
* Standardize data using the Standard Scaler (Ln 15). 
*
## Reducing Dimensions using PCA (Ln 16 - 17)
In this section we: 
* Use PCA to reduce dimensions to 3 principal components(Ln 16). 
* Create a DataFrame with the principal components data (Ln 17). 

## Clustering Cryptocurrencies using K-means (Ln 18-21) 
In this section we: 
* Find the best value for K using the elbow curve (Ln 18). Please refer to Ln18_plot.png for the elbow curve visualization. 
* Create a function to run  K-Means with k=5 being our best value for k(Ln 19).
* Look for clusters the first best value of k, where k=5, and store our results in a dataframe named 'five_clusters_rev' (Ln 20).
* Merge five_clusters_rev with crypto_df_rev  to create clustered_df (Ln 21).

## Visualizing Results (Ln 22- 23) 
In this section we: 
* Scale data to create the scatter plot, using sklearn's MinMaxScaler (Ln 22). 
* Plot the scatter with x="TotalCoinsMined" and y="TotalCoinSupply"(Ln 23). Please see Ln23_plot.png for the visualization. 
*
## Table of Cryptocurrencies (Ln 24-25) 
In this section we: 
* Create a data table with tradable cryptos, using our clustered_df as our input (Ln 24).
* Print the total number (532) of unique tradable cryptocurrencies (Ln 25).
