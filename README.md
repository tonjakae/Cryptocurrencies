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

![image](https://user-images.githubusercontent.com/87340105/155916194-4c4e8881-f2be-4f51-b81c-7fc70cda7c29.png)

* Drop the IsTrading column.

![image](https://user-images.githubusercontent.com/87340105/155916288-75c08e35-fe8d-41eb-86f6-8b8c32c74be8.png)

* Remove rows that have at least one null value.

![image](https://user-images.githubusercontent.com/87340105/155916259-ac6db97d-d916-48b6-81a4-e2a8ae07a551.png)

* Filter the crypto_df DataFrame so it only has rows where coins have been mined.

![image](https://user-images.githubusercontent.com/87340105/155916354-967df177-64ce-4dab-82e6-80fc67af95da.png)

* Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.

![image](https://user-images.githubusercontent.com/87340105/155916375-b2c44097-28c4-4822-9cc9-bb9386422265.png)

* Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.

![image](https://user-images.githubusercontent.com/87340105/155916405-5ffe2b08-60c2-42de-b02e-fa95a59518ab.png)

