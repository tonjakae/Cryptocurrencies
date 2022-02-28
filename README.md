# Cryptocurrencies: Module 18 Analysis

## Overview
Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of our most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked me to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

### This new assignment consists of four technical analysis deliverables:
* Deliverable 1: Preprocessing the Data for PCA
* Deliverable 2: Reducing Data Dimensions Using PCA
* Deliverable 3: Clustering Cryptocurrencies Using K-means
* Deliverable 4: Visualizing Cryptocurrencies Results

## Deliverable 1: Preprocessing the Data for PCA

### 1.) Keep all the cryptocurrencies that are being traded.

![image](https://user-images.githubusercontent.com/87340105/155916194-4c4e8881-f2be-4f51-b81c-7fc70cda7c29.png)

### 2.) Drop the IsTrading column.

![image](https://user-images.githubusercontent.com/87340105/155916288-75c08e35-fe8d-41eb-86f6-8b8c32c74be8.png)

### 3.) Remove rows that have at least one null value.

![image](https://user-images.githubusercontent.com/87340105/155916259-ac6db97d-d916-48b6-81a4-e2a8ae07a551.png)

### 4.) Filter the crypto_df DataFrame so it only has rows where coins have been mined.

![image](https://user-images.githubusercontent.com/87340105/155916354-967df177-64ce-4dab-82e6-80fc67af95da.png)

### 5.) Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.

![image](https://user-images.githubusercontent.com/87340105/155916375-b2c44097-28c4-4822-9cc9-bb9386422265.png)

### 6.) Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.

![image](https://user-images.githubusercontent.com/87340105/155916405-5ffe2b08-60c2-42de-b02e-fa95a59518ab.png)

### 7.) Use the get_dummies() method to create variables for the two text features, Algorithm and ProofType, and store the resulting data in a new DataFrame named X.

![image](https://user-images.githubusercontent.com/87340105/155916698-865d3a76-dc56-4524-861c-7860d06467cb.png)

### 8.) Use the StandardScaler fit_transform() function to standardize the features from the X DataFrame.

![image](https://user-images.githubusercontent.com/87340105/155916725-807ac384-32f2-478c-8181-27519d527686.png)

## Deliverable 2: Reducing Data Dimensions Using PCA

### 1.) Apply PCA to reduce the dimensions to three principal components.

![image](https://user-images.githubusercontent.com/87340105/155916862-cebaf284-fe41-40ef-8084-c15c8f2d480e.png)

### 2.) Create a new DataFrame named pcs_df that includes the following columns:
* PC 1, PC 2, PC 3
* Uses the index of the crypto_df DataFrame as the index.

![image](https://user-images.githubusercontent.com/87340105/155916962-9f16359a-4627-44f4-97ca-1d95906fb4ab.png)

## Deliverable 3: Clustering Cryptocurrencies Using K-means

### 1.) Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K.

![image](https://user-images.githubusercontent.com/87340105/155917469-9fe870d2-fd73-4d6a-a3d4-67bfa94f3d13.png)
![image](https://user-images.githubusercontent.com/87340105/155917517-4e668761-176a-4207-9a1e-52190a0504b4.png)

### 2.) Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K.

![image](https://user-images.githubusercontent.com/87340105/155917336-5105c259-3be8-4768-ad19-7f37bdfda347.png)

### 3.) Use the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.
### 4.) Create a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns. The index should be the same as the crypto_df DataFrame.
### 5.) Add the CoinName column that holds the names of the cryptocurrencies, which you created in Step 7 of Deliverable 1, to the clustered_df.
### 6.) Add another new column to the clustered_df named Class that holds the predictions, i.e., model.labels_, from Step 3.

![image](https://user-images.githubusercontent.com/87340105/155917585-a9af00c1-af20-4f2c-a44c-2c2cbea31c70.png)

![image](https://user-images.githubusercontent.com/87340105/155917603-dfbde660-6d87-45a6-95e4-f4d04924c1ab.png)

## Deliverable 4: Visualizing Cryptocurrencies Results

### 1.) Create a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.

![image](https://user-images.githubusercontent.com/87340105/155918039-1872e95c-aa34-4b3a-91b8-607f68b16e3d.png)

### 2.) Add the CoinName and Algorithm columns to the hover_name and hover_data parameters, respectively, so each data point shows the CoinName and Algorithm on hover.

![image](https://user-images.githubusercontent.com/87340105/155918141-501303c8-621a-43b7-99b7-e441187d1e55.png)

### 3.) Create a table with tradable cryptocurrencies using the hvplot.table() function.

![image](https://user-images.githubusercontent.com/87340105/155919237-b025994e-39d9-46dd-bff6-d210a6aba720.png)

### 4.) Print the total number of tradable cryptocurrencies in the clustered_df DataFrame.

![image](https://user-images.githubusercontent.com/87340105/155919398-637a85f2-49e4-4a2a-80e5-f4088e783c09.png)

### 5.) Use the MinMaxScaler().fit_transform method to scale the TotalCoinSupply and TotalCoinsMined columns between the given range of zero and one.

![image](https://user-images.githubusercontent.com/87340105/155919428-ecefdd18-562f-494e-88db-4738b5594169.png)

### 6.) Create a new DataFrame using the clustered_df DataFrame index that contains the scaled data you created in Step 5.

![image](https://user-images.githubusercontent.com/87340105/155919453-a3199774-abf6-4a23-91eb-06c9f8809a20.png)

### 7.) Add the CoinName column from the clustered_df DataFrame to the new DataFrame.

![image](https://user-images.githubusercontent.com/87340105/155919502-aa393e99-751b-4a75-bdfb-9c96a5d071ce.png)

### 8.) Add the Class column from the clustered_df DataFrame to the new DataFrame.

![image](https://user-images.githubusercontent.com/87340105/155919570-1db7b6e6-a2d0-4be8-85ae-3e35f13e3a2e.png)

### 9.) Create an hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class", and have it show the CoinName when you hover over the the data point.

![image](https://user-images.githubusercontent.com/87340105/155919639-29ce1f48-d70e-4a09-8b74-e8b53e25aae3.png)

![image](https://user-images.githubusercontent.com/87340105/155919759-09e860ae-1809-43e5-96ad-31327078535a.png)


