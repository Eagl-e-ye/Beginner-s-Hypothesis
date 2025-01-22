Beginner’s Hypothesis

~Indranil Singha 24112054


This is the manual to understand the code properly.
The code I have provided is of the best model of the many models I have made and is giving 0.94 points in the leaderboard but due to late submission the rank is not considered. I have divided the project into 7 jupyter notebooks of which 5 are for different models to predict 5 different columns of the csv to understand and execute the work properly.
Notebooks:
1.	Feature extraction: for this notebook I used Kaggle to access the GPU P100. I used the resnet50 model to preprocess and extract the features of 10k videos of 20-frames 64x64. The open cv module was used to read the frames and by removing the last head layer I derived the features of the 10000 videos and saved it in array. The images of the frames are transformed with gaussian blur and grayscale to detect the edges more efficiently. This notebook is also used to extract the features of the test videos by slightly changing the code of the model.
2.	Element: This notebook is for the model which is trained to detect the values of element column for the test videos. The element names are label encoded and is trained with logistic regression which gave an evaluation accuracy of 100%. The label encodes and the model is saved with .pkl for further use.
3.	Motion: this notebook is for the model which is trained to detect the values of motion column for the test videos. Here also the motion is label encoded, and logistic regression is used to train the model, and this gave an evaluation accuracy of 98.9% on seen data. The label encodes and the model are saved with .pkl for further use.
4.	Power: this notebook is for the model which is trained to detect the values of power column for the test videos. Since these data contained noise or outliers, those needed to be removed. At first the number of occurrences of all the values in power was checked and the outliers could be identified with very less occurrences. The model is trained with only 5 different types of powers, and the training data is extracted from the rgb values of the titan in the videos. The model gave eval accuracy of 100% on seen data. The powers are label encoded and saved for further use.
5.	Speed: this notebook is for the model which is trained to detect the values of speed of the titans. There are 2 speeds of titans, so the speed was label encoded and XGBClassifier is used to train the model. This gave accuracy of 100% on 20% seen data. The label encodes and the model are saved with .pkl for further use.
6.	Summary: this notebook is for the model which is trained to detect the values of summary columns. The X_values and Y_values were separated to train the model with the video features extracted before. The X and Y models are trained separately with random forest and gave little error of 5-6 on seen data. 
7.	Final arrangement- this notebook is the final notebook which is used to load all the models, label encodes and the test videos. The predictions are decoded with the help loaded encodes. The final csv file is created at the end after predicting all the values of all columns.

