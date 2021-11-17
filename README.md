# Block-Millionaires
This repository informs about the computational processes conducted for training ANNs to predict the accredited investor status of Ethereum EOAs.

An overview can be found in: https://github.com/KennyLoRI/Block-Millionaires/blob/main/OverviewDataProcessing.png

## Reading Guide
The whole data preprocessing, transaction enrichment and feature engineering process was conducted two times. 
1. For a data set of individuals who have reported and proven their net worth which has eventually been used to determine the accredited investor status. 
2. A data set of individuals which have not reported any kind of net worth level. Under the assumption of heavily right skewed wealth distributions, all of them were labled as non-accredited investors (sth. that should not be done in case this project will be repeated).

- The code for (1) can be found in "FeatureEng(Data1)-Censored.ipynb"
- The code for (2) is the same as for 1 except for the addresses used and the export functions storing the resulting dataframes. However, as this step needed to be censored in order to protect the privacy of the addresses the code of 1 should be sufficient.

After (1) and (2) was conducted, all transactions were available for creating the transaction graph needed to create Node2Vec embeddings for all source addresses. This is done in "Node2VecEmbedding-Censored.ipynb". This step was censored as well such that no addresses are depicted.

The resulting dataframes can be found in: 
1. y_testNonOver_8_3.csv
2. X_testNonOver_8_3.csv
3. y_trainNonOver_8_3.csv
4. X_trainNonOver_8_3.csv
The source addresses and the actual edge list of transactions can out of data privacy reasons not be published.

Taking the the resulting dataframes, the models were created and evaluated in "FinalModel_train_01-10.ipynb". 

The resuls of the modelling procedures per network architecture are stored in: 
1. DF_8Lay_scores_sorted23_10.csv
2. DF_4Lay_scores_sorted24_10.csv
3. DF_10Lay_scores_sortedBigger22_10.csv
4. Scores_2Layered23_10.csv




