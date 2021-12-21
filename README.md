# Cryptocurrencies

## Overview
Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. Create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data not ideal, needed to be processed to fit the machine learning models. To group the cryptocurrencies, it was decided to use a clustering algorithm and data visualizations to share her findings with the board.

## Data Processing
The crypto_data.csv was retrieved from CryptoCompare (https://min-api.cryptocompare.com/data/all/coinlist)
The data was cleaned and processed to keep all cryptocurrencies that are currently being traded and have coins that are being mined currently.
This resulted in 532 cryptocurrencies available for analysis.
![D1-1](https://github.com/ASCHEET/Cryptocurrencies/blob/main/Resources/D1-1.png?raw=true)

The name of the crypto was removed from the DataFrame and the Get_dummies method was used to convert categorical variable into dummy/indicator variables into a new DataFrame named X.
![D1-3](https://github.com/ASCHEET/Cryptocurrencies/blob/main/Resources/D1-3.png?raw=true)

The PCA algorithm was used to reduce the dimensions of the X DataFrame down to three principal components into a pcs_df DataFrame that has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame.
![D2-1](https://github.com/ASCHEET/Cryptocurrencies/blob/main/Resources/D2-1.png?raw=true)

## Results
Using the pcs_df DataFrame, an elbow curve using hvPlot was created to find the best value for K.  As shown below k=4 clusters was optimum.
![D3-1](https://github.com/ASCHEET/Cryptocurrencies/blob/main/Resources/D3-1.png?raw=true)

Next, the pcs_df DataFrame was used to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.

![D3-2](https://github.com/ASCHEET/Cryptocurrencies/blob/main/Resources/D3-2.png?raw=true)

A new DataFrame was created named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns, the CoinName column was added from coinname_df DataFrame. Another new column to the clustered_df named 'Class' that holds the predictions, i.e., model.labels_
The unsupervised machine learning algorithm Principal Component Analysis (PCA) was used to reduce the dimensions of the cryptocurrency components to three principal components.  

The following 3D scatter chart shows the cryptocurrency dataset in four clusters.
![D4-1](https://github.com/ASCHEET/Cryptocurrencies/blob/main/Resources/D4-1.png?raw=true)

The 2D scatter chart shows each cryptocurrency from the dataset as it related to total coins mined and total coin supply.

![D4-4](https://github.com/ASCHEET/Cryptocurrencies/blob/main/Resources/D4-4.png?raw=true)














