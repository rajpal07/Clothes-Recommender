Aim of the project

To recommend a list of similar clothing images from the dataset based on the input image of the apparel.

This project is an open one page content-based system where users can search for similar apparels/ clothing by uploading the apparel’s image .
The clothe recommender system is a system that seeks to predict similar images according to users input 

Clothe Recommender system is divided into 3 parts:

1) App : Model creation , Feature extraction , Creation of Pickle files (images.pkl , imgFeatures.pkl)

2) Vector comparison : Returns euclidean distances and indices between vectors using NearestNeighbour 

3) Hosting : Hosting on local machine and embedding the algorithm on to a website using StreamLit framework .

App

The app.py file consists of model creation wherein a model with an additional top layer (GlobalMaxPooling) is created , using existing data-set which is of shape (224,224,3) and is locally available on the local machine . 
Feature extraction function 
Takes an input of an RGB image 
Converts it into an 3D array 
Expands the 3D array dimension to 4D array dimension using numpy array which helps to take input in batches and 
preprocess the image so that the image is compatible to be an input image for resNet module which is trained on imageNet module
Predict the expanded 4d array
Lastly flatten the 4D array to 1D array with shape of (1,2048) 
And returns a normalized result (where all the values of array are between 0-1)

Pickle Dump is used to dump all the features in imgFeatures.pkl and names of the images in images.pkl . Pickle was created so that I can reuse them to find out distances and also while displaying images on web app.


Distances

This module uses NearestNeighbours to return and saves distances between vectors and indices of that specific file which are used to predict and recommend similar products .

Hosting

Hosting was mainly done using StreamLit in this project .With the help of StreamLit I uploaded and saved the image on local machine
To give users a friendly and customized experience, a rating system has also been incorporated using streamlit , where a slider is used to represent stars(marking system).
