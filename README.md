# Cryptocurrencies: Module 18 Analysis

## Overview
Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of our most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked me to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

### This new assignment consists of four technical analysis deliverables:
* Deliverable 1: Preprocessing the Data for PCA
* Deliverable 2: Reducing Data Dimensions Using PCA
* Deliverable 3: Clustering Cryptocurrencies Using K-means
* Deliverable 4: Visualizing Cryptocurrencies Results

## Deliverable 1: Preprocessing the Data for PCA
* Keep all the cryptocurrencies that are being traded.
* Drop the IsTrading column.
* Remove rows that have at least one null value.
* Filter the crypto_df DataFrame so it only has rows where coins have been mined.
* Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
* Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.
