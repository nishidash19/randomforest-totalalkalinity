# randomforest-totalalkalinity
Code was based on 2022 NOAA GLODAP data (https://www.ncei.noaa.gov/data/oceans/ncei/ocads/data/0257247/). RFR model is based on Empirical Seawater Property Estimation Routines (ESPER) equation 1 (https://aslopubs.onlinelibrary.wiley.com/doi/10.1002/lom3.10461) and currently trained only on the Pacific Ocean. An initial Gaussian Mixture Model (GMM) clustering prestep was followed by a random forest regression model. 

The code is still under development for use as a complete data product, however if anyone is interested in training this on a different ocean, the code in "TA_optimal_clustering_functions" can be adapted to a different dataset to determine how many clusters are needed for a specific ocean. 

Code "TA_initial_data_processing" will help get GLODAP data into the correct format to that can be used an input to the code in this repo. 

The rest of the code is based on 8 clusters (full covariance in the GMM) in the Pacific Ocean. Code for the GMM prestep and RFR model is in the "GMM_RFR_TA" file. There is code to create overlapping clusters, where points can be in more than 1 cluster to make a more robust model. "ta_cv" is code used to get the bias and RMSE estimates for 5 fold cross validation. "8cl_ESPER_comparison_fin" has the code to compare the RFR predictions with predictions from neural networks and locally interpolated regressions. 

