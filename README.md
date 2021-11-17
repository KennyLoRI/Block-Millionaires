# Block-Millionaires
This repository informs about the computational processes conducted for training ANNs to predict the accredited investor status of Ethereum EOAs.

An overview can be found in: https://github.com/KennyLoRI/Block-Millionaires/blob/main/OverviewDataProcessing.png

Yet, the practical implementation was not as streamlined as described in the overview illustration. 
The whole data preprocessing, transaction enrichment and feature engineering process was conducted two times. 
(1) For a data set of individuals who have reported and proven their net worth which has eventually been used to determine the accredited investor status. 
(2) A data set of individuals which have not reported any kind of net worth level. Under the assumption of heavily right skewed wealth distributions, all of them were labled as non-accredited investors (sth. that should not be done in case this project will be repeated).

The code for (1) can be found in "FeatureEngineering_wo_Node2Vec(Data1).ipynb"
The code for (2) can be found in "FeatureEng_wo_Node2Vec(Data2).ipynb"

After (1) and (2) was conducted, all transactions were available for creating the transaction graph needed to create Node2Vec embeddings for all source addresses. This is done in "Node2VecEmbedding.ipynb". 

Taking the the resulting data frames, the models were created and evaluated in "FinalModel_train_01-10.ipynb". 

The final data set can be found in the repository as well. Yet everything is anonymized such that the source addresses are not published.


