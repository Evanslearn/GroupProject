# GroupProject on Synthetic Data Generation

In this repository, we attach an ipynb, that contains the code used for data generation through SDV (Group Project SDV.ipynb). To use it, you can simply run all cells in Google Colab, but you could also modify variables, according to the instructions:

## Choosing a Dataset
* If you intend to use the creditcardfraud dataset, this must first be uploaded, since the file was too large to be uploaded in github (150MB). The file can be found here:
https://drive.google.com/file/d/1yTbOW4-TF_ogj5rii_aB30LeyKFMXKDq/view?usp=sharing \
You can then uncomment the line [initialData, df_train, df_test, useCreditCard] = useCreditCardData(useFraudData = "useFraud", numberOfSyntheticRows = "rowsLikeTrainSet"), and choose values for the variables:
  * useFraudData = "useFraud": Use this value, if you only want to create data from the fraud class. Else change this value to any other string.
  * numberOfSyntheticRows: Change this value, to show how many synthetic samples you want to create. Default string value ("rowsLikeTrainSet"), will end up creating rows equal to the original data train set.
* If you intend to use the Health Insurance Lead Prediction dataset, you simply need to comment the line "[initialData, df_train, df_test, useCreditCard] = useCreditCardData(useFraudData = "useFraud", numberOfSyntheticRows = "rowsLikeTrainSet")"

## Number of synthetic Data:
By default, the number of synthetic data will be equal to the train set (70% of the initial data). If you would like to change this, simply change the value of the variable numberOfSyntheticRows, to the value of choice.

## Choosing a Synthesizer
* To choose a synthesizer, you can change the value of synthesizer = "GaussianCopula", to be one of the 4 values: "GaussianCopula", "CTGAN", "CopulaGAN", "TVAE"
* If you do not choose, the default value is "GaussianCopula"

## Choosing dataset to train the Random Forest, kNN, Logistic Regression Models.
The choices here are datasetToUse = "Synthetic", "InitialTrain", "Combined". By default, I have set datasetToUse = "Combined"

# Results
* Running the data synthesizing process gives results of metrics about the trend and pattern similarity of the original and the synthetic data, like this:
![image](https://github.com/Evanslearn/GroupProject/assets/104510165/b573f859-e9e9-4ffd-9310-41663e91cac0)
Note: GaussianCopula Synthesizer for Health Insurance Lead Prediction dataset.

* We can also plot the distributions of Real vs Synthetic data, for any feature, and 6 example features look like this:
![image](https://github.com/Evanslearn/GroupProject/assets/104510165/22b2838b-e028-4b71-9681-943ed95fc2e0)
 Note: GaussianCopula Synthesizer for Health Insurance Lead Prediction dataset.

