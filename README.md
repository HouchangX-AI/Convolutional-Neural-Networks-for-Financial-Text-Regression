# Convolutional-Neural-Networks-for-Financial-Text-Regression

创新工场金融项目：Financial volatility forecasting from annual reports

## Data

The dataset from Tsai et al. (2016) includes 10-K reports available on the U.S. Security Exchange Commission (SEC) Electronic Data Gathering, Analysis and Retrieval (EDGAR) website2. Following previous works (Kogan et al., 2009; Wang et al., 2013; Tsai and Wang, 2014; Tsai et al., 2016), section 7, Management’s Discussion and Analysis (MD&A) is used instead of the complete 10-K report.
The dataset also includes a volatility value for each report of 12 months after the report is published. The volatility value in the dataset is the natural logarithm of stock return volatility and used as the prediction target.

## Model

1. CNN-baseline 
2. CNN-STC
3. CNN-NTC
4. CNN-STC-multichannel
5. CNN-NTC-multichannel

Final hyperparameters are selected as mini-batch size 10, fixed text length 20000, convolution layer kernels 3, 4 and 5 with 100 output features, probability of dropout layer 0.5, and learning rate 0.001.

## Evaluation

1. MSE
2. Spearman's rank correlation (evaluate the ranking performance of a model)
