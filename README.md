IDENTIFYING IF THERE IS ONE SPEAKER OR MORE THAN ONE SPEAKER IN ANY GIVEN AUDIO



INTRODUCTION:

In this project we are going to identify that if there is one speaker or more than one speakers in an audio. This is the problem statement given from Infosys Summer of Ideas. 

DATASET:

We have downloaded Audio Speeches from various sources. Our Audio data comprises of Audio speeches of 5 different persons. As this is the task of identifying one or more than one speaker so Audio Speeches of more than one person is the Prime need. 


DATA PREPARATION:

Our approach emphasizes on Supervised Learning Technique. We are going to make a Binary classifier which is going to classify whether in an audio there is one speaker or more than one. So we have raw audio speeches of five different persons. We are dividing all our audios into two classes which is 0 for one speaker and 1 for more than one speaker. 

Talking about first class, audio samples can be easily prepared for that. Raw audio samples will contribute to the first class. To make audio samples belong to second class, we have overlapped k audio samples of two different speakers. For example if there are 500 audio speeches of two different speakers, we will take one audio from first perosn and another audio from second perosn and overlap both of them. By overlapping, in the resulting audio will be in which the two different apeakers speak concurrently. So, we have itterated this step for k number of audio samplles resulting in k number of overlapped audios.
It's not necessary that two speakers speak on the same time. Rather, two speakers can speak one after another.To achieve that we have joined the audio of two different persons. So, in the resulting audio we will have two different speakers speaking one after the other. 
Now, we have two different types of Audio samples.


FEATURE EXTRACTION:

To extract the features from Audio files, we have used a Python library called Librosa. We are extracting raw Chromagram Features of all the audios. Chromagram features are 12 different audio notes which are present in an audio. These all features are tranformed into a Dataframe which now can be input to a Deep Nueral Network Model. 


FEATURE ENGINEERING:

As we are having 12 features, it would be a good idea to reduce or to increase number of features. We have reduced the number of features to 10. Number of features is something we can play with. 


MODELLING:

Now data has to be fed into a Deep Neural Network for classification. Our DNN is having 5 Layers(One input, one output, and three hidden Layers). We have kept number of Neurons in Input layer as 128 for better learning of the pattern in data. Hidden layers have activation function as 'Leaky ReLU'. The purpose of using LeakyReLU is to overcome the problem of Overfitting. Output layer is having single Neuron with activation function as 'Sigmoid' since it as binary classification task. Loss is used as 'binary_crossentropy'. Optimizer is 'adam'.


TRAINING:
We have trained for 10 Ephochs having a Batch Size of 16. We split the data into Training and Testing. 0.33% of data was kept for testing. 


EVALUATION:

We are getting Training Accuracy at 96% and Validation Accuracy as 94%.


TESTING:

We tested our model on real world dataset, which the model has not even seen. Our model was able to correctly  classify 7 out of 11 Audio samples.