# Unsupervised Machine Learning with Cryptocurrencies
## Overview
The objective of this project was to analyze cryptocurrencies that are on the trading market and how they could be grouped to create a classification system for this new investment. Since there is no known output for the project, unsupervised machine learning was used to group cryptocurrencies using a clustering algorithm. 

### Tools
* Python
* Pandas
* hvPlot
* Plotly
* SkLearn

## Summary
The original crypto data had a variety of data types, so it was pre-processed by:
  1) filtering for crypto stocks currently trading 
  2) dropping any rows with null values
  3) dropping "CoinName" and "IsTrading" columns that were no longer relevant and string data types

Then the get_dummies function was used to convert the 'Algorithm' and 'ProofType' columns to integer data types. The data was then normalized with the sklearn StandardScaler() function. Since the get_dummies function increased the dimension of the data to 100 columns, PAC was performed to reduce the dimensions to three components for each trading crypto stock. 

![Screen Shot 2021-07-04 at 6 47 44 PM](https://user-images.githubusercontent.com/69849998/124401617-54f0cf00-dcf8-11eb-8fbf-e3069d078b2e.png)

The PCA crypto data was then plotted using an elbow curve - which demonstrates that the best value for K is 4. 

![Screen Shot 2021-07-04 at 6 33 35 PM](https://user-images.githubusercontent.com/69849998/124401641-75b92480-dcf8-11eb-984f-ff7de39c931f.png)

The K-means model was then initialized, and fitted to the the PCA crypto data to predict the clusters. These cluster predictions were concatenated in to a dataframe with the crypto data, and the three principle components. Below is a Plotly Express scatter plot of the concatenated dataframe. 

![Screen Shot 2021-07-04 at 6 33 08 PM](https://user-images.githubusercontent.com/69849998/124401698-d6e0f800-dcf8-11eb-9cc5-512b8e9caf7d.png)

The columns of the "TotalCoinSupply" and "TotalCoinsMined" in the clustered crypto data was then normalized using sklearn's MinMaxScaler(). Below is an hvPlot scatterplot of the two columns with each class/cluster represented by a different colour. 

![Screen Shot 2021-07-04 at 6 32 18 PM](https://user-images.githubusercontent.com/69849998/124401786-6686a680-dcf9-11eb-99cb-542e4d5a7a33.png)
