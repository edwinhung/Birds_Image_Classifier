# Installation
Training process of neural network was done in Google Colab. Installation/Upgrade of fastai and timm library may be needed with the following command:

    pip install fastai timm

# Motivation
Often time we encounter a beautiful bird outdoor and are curious about which species it belongs to. The objective of this project is to build a web app that anyone can use to get a quick answer about bird species on an image.

# Dataset
[BIRDS 400](https://www.kaggle.com/datasets/gpiosenka/100-bird-species) on Kaggle contains a total of 62388 images of 400 bird species.

# Training neural network with fastai
Thanks to the great [dataset](https://www.kaggle.com/datasets/gpiosenka/100-bird-species) on Kaggle, this project trains a neural network with fastai API. Transfer learning is used with pre-trained efficient net from the convenient timm library (timm is now integrated into fastai after this project was completed, please check out [timm.fast.ai](https://timm.fast.ai/)). The result is an impressive 99.4% accuracy on given test set*.

*see notes from Kaggle dataset provider

# Deployment
The deep learning model is hosted on severless Azure Function which accepts http request. Prediction result from Azure Function can then be consumed by the web app hosted on Heroku. 

# File Description
- Birds_400_model.ipynb: a notebook with neural network training procedure. 
- Birds_Azure_Function: a folder containing files for Azure Function deployment
- Heroku: a folder to build web app with Voila and Heroku.

# Result
The Heroku web app can be found [here](https://birdclassifier.herokuapp.com/). Feel free try it out and see how the model performs.


# Acknowledgement
- This project was inspired by Luiz Santos's post on medium, [Training an image classifier on FastAi and deploying it to Android using ONNX](https://medium.com/@luizhss/training-an-image-classifier-on-fastai-and-deploying-it-to-android-using-onnx-b1e3d95a8425), which showcased the ease of training neural network using fastai. 
- This great [guide](https://medium.com/pytorch/efficient-serverless-deployment-of-pytorch-models-on-azure-dc9c2b6bfee7) by Gopi Kumar shows step-by-step tutorial to deploy fastai model on Azure Function.
- Here is the [guide](https://course.fast.ai/deployment_heroku) from fastai to build a interactive web app with Voila and Heroku.
