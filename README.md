# MachineLearningBitcoin

## About 
The goal of this project was to predict the price of the Bitcoin using machine learning. It is based on the following tutorials : 
1. https://machinelearningmastery.com/machine-learning-in-python-step-by-step/ 
2. https://www.dataquest.io/blog/python-api-tutorial/
3. https://www.codespeedy.com/pipeline-in-machine-learning-with-scikit-learn-in-python/ 

In order to train the algorithms, the dataset from https://www.kaggle.com/team-ai/bitcoin-price-prediction/version/1 was used. The project was in big part inspired by the following notebook : https://www.kaggle.com/terrifictitan12/bitcoin-price-prediction. Although in our case, the parsing of the data was different, rather than using only the data from one day to predict the bitcoin price, we used the data from the week before and finally, our project encompassed an API allowing to predict the bitcoin price using data up to date. 

## Prerequisites 
The program works with Python3. 
It is written using a Jupyter Notebook as such to run it, it is recommended to install Jupyter and to run it with it.  

## Instruction 
1. Install Jupyer Notebook. This can be done using pip install or Anaconda. 
2. Download the necessary libraries. Those are : 
  a. math
  b. pandas 
  c. numpy
  d. sklearn 
  e. matplotlib.pyplot
  f. datetime
  g. requests 
3. Download the file MachinLearning_final.ipynb and the file bitcoin_prices_train.csv. Make sure to place them in the same file so that the path between the two file remains the same. 
4. Run the code and access the results through the jupyter notebook. 

## Description 
We begin by installing the necessary libraries. Following this, we analyse the dataset and observe how the data is structured with the help of the panda library and some visualization. 

Once the data has been visualized and understood, we prepare it so that it is suited for the machine learning algorithms. To do this, we mainly have to suppress the comas present in some of the number and then to suppress the column encompassing the date as it is not relevant to predict the Bitcoin price. We then create two dataframes, one having the data from the previous week for each row and the other having the data to the subsequent day for each rows. Finally we separate our data in order to use 90% of it for training our algorithms and the following 10% to test them. 

After the data has been prepared, we set our algorithm by using the pipeline library. The algorithms themselves and the scaler used to scale the data for the algorithms all come from the sklearn library. 

We then apply the algorithms to our data in order to train them. To test them we use the R^2 score indicator, the ensuing comparison between each of the algorithms shows us that the MLP regression works poorly with our data but that the passive aggresive regression and the SGD regression are rather effective in their prediction. 

Finally, to predict the price of the Bitcoin, we used an API to obtain the data of the current previous week which we then input in our passive aggresive regression algorithm in order to obtain a prediction. 
