# Convolutional-Neural-Networks-for-Financial-Text-Regression

创新工场金融项目：Financial volatility forecasting from annual reports

复现自acl paper [Convolutional-Neural-Networks-for-Financial-Text-Regression](https://www.aclweb.org/anthology/P19-2046.pdf).



## Data

The dataset from Tsai et al. (2016) includes [Extended 10-K Corpus](https://clip.csie.org/10K/data) available on the U.S. Security Exchange Commission (SEC) Electronic Data Gathering, Analysis and Retrieval (EDGAR) website2. Following previous works (Kogan et al., 2009; Wang et al., 2013; Tsai and Wang, 2014; Tsai et al., 2016), section 7, Management’s Discussion and Analysis (MD&A) is used instead of the complete 10-K report. 

The dataset also includes a volatility value for each report of 12 months after the report is published. The volatility value in the dataset is the natural logarithm of stock return volatility and used as the prediction target.

## Model

1. CNN-baseline 
2. CNN-STC
3. CNN-NTC
4. CNN-STC-multichannel
5. CNN-NTC-multichannel

Final hyperparameters are selected as mini-batch size 10, fixed text length 20000, convolution layer kernels 3, 4 and 5 with 100 output features, probability of dropout layer 0.5, and learning rate 0.001.

## Results

| Model                 |    2008    |    2009    |    2010    |    2011    |    2012    |    2013    |     Avg    |
|-----------------------|:----------:|:----------:|:----------:|:----------:|:----------:|:----------:|:----------:|
| CNN-simple (baseline) | **0.3716** |   0.4708   | **0.1471** |   0.1312   |   0.2412   |   0.2871   |   0.2748   |
| CNN-STC               |   0.5358   |   0.3575   |   0.3001   |   0.1215   |   0.2164   |   0.1497   |   0.2801   |
| CNN-NTC-multichannel  |   0.5077   |   0.4353   |   0.1892   |   0.1605   |   0.2116   |   0.1268   |   0.2718   |
| CNN-STC-multichannel  |   0.4121   |   0.4040   |   0.2428   |   0.1574   |   0.2082   |   0.1676   |   0.2653   |
| CNN-NTC               |   0.4672   | **0.3169** |   0.2156   | **0.1154** | **0.1944** | **0.1238** | **0.2388** |

Performance of different models(from paper), measured by Mean Square Error (MSE). Lower is better and **boldface** shows the  best result among presented models for the corresponding column. 

