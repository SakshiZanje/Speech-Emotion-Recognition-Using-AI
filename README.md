# Speech-Emotion-Recognition-Using-AI

Speech is the best and normal way of communication amongst human. We are depended so much on it that we recognize its importance when it comes to use of other communicating ways, such as emails or text messages. Emoji have become common in text messages, because the meaning of messages could be misunderstood sometimes and we have to pass emotions along with the messages as we do in speech. Since emotions help us to understand each other better, a natural outcome is to extend this understanding to computers.7

The speech emotion recognition aims to recognize the emotional state of a person through his/her voice automatically. The main focus of this system is to deliver automation in classifying audio files into different core emotions which helps different sectors to provide better facilities to their clients.

The primary aim of this work is to train and evaluate the classification performance of the suitable deep learning model for emotion detection and classification of eight kinds of emotions that are core emotions of every human being which are neutral, calm, sadness, happiness, fearful, disgust, angry and surprised. 

In this study we attempt to detect common discrete emotions by extracting features like Mel Frequency Cepstral Coefficients (MFCCs) using Support Vector Machine (SVM) and Convolutional Neural Network (CNN).

# System Architecture
Fig. represents our proposed system architecture. Here, In First phase I have used RAVDESS and TESS dataset from which audio files are loaded and in second phase feature extraction is done using Librosa library and their features and labels are stored variables in working folder. Then in third phase dataset is splitted into training and testing dataset by loading the features and their respected labels. Then in fourth Phase training and classification is done using CNN model. Classification is done by predicting into 8 emotions.
![System architecture](https://user-images.githubusercontent.com/69428803/122646233-c8f97780-d13b-11eb-926b-6b789d4008cb.PNG)

# Two datasets used here are:

# 1. RAVDESS (Ryerson Audio-Visual Database of Emotional Speech and Song)
1440 speech files and 1012 Song files from RAVDESS. This dataset includes recordings of 24 professional actors (12 females, 12 males), vocalizing two lexically-matched statements in a neutral North American accent. Speech includes calm, happy, sad, angry, fearful, surprise, and disgust expressions. From this we have used only speech files.

# 2. TESS (Toronto Emotional Speech Set)
2800 files from TESS. A set of 200 target words were spoken in the carrier phrase "Say the word _' by two actresses (aged 26 and 64 years) and recordings were made of the set portraying each of seven emotions (anger, disgust, fear, happiness, pleasant surprise, sadness, and neutral). There are 2800 stimuli in total. Two actresses were recruited from the Toronto area. Both actresses speak English as their first language, are university educated, and have musical training. Audiometric testing indicated that both actresses have thresholds within the normal range.

You can download RAVDESS dataset from this link:
https://www.kaggle.com/uwrfkaggler/ravdess-emotional-speech-audio

You can download TESS dataset from this link:
https://www.kaggle.com/ejlok1/toronto-emotional-speech-set-tess

# Filename identifiers
Modality (01 = full-AV, 02 = video-only, 03 = audio-only).
Vocal channel (01 = speech, 02 = song).
Emotion (01 = neutral, 02 = calm, 03 = happy, 04 = sad, 05 = angry, 06 = fearful, 07
= disgust, 08 = surprised).
Emotional intensity (01 = normal, 02 = strong). NOTE: There is no strong intensity
for the ‘neutral’ emotion.
Statement (01 = “Kids are talking by the door”, 02 = “Dogs are sitting by the door”).
Repetition (01 = 1st repetition, 02 = 2nd repetition).
Actor (01 to 24. Odd-numbered actors are male, even-numbered actors are female).

Here, SVM and CNN model is used for our project. Code for SVM and CNN are their in each folder. 

# Steps for the project: 

1. Merging Dataset file is used to merge two datasets such as RAVDESS and TESS into one folder by adding Actor_25 and Actor_26. OAF and YAF folder files of TESS dataset are moved to Actor_25 and Actor_26 folder.
2. As our dataset is recorded one so I have not used any preprocessing steps for it and I directly moved for feature extraction step. In SVM and CNN folder feature extraction is done differently. Along with training and testing is done in the following code.
3. Audio Recorder file is for recording the audio in .wav extension. We can check our model is working properly or not by testing it. Test Audio file has audio file for testing purpose.  


# CNN Architecture
The convolution neural network architecture is used for classification of emotions from speech. The network is able to work on 40 features of each audio file. We provide a number of training files shape of 40 x 1 on which one round of CNN with activation ReLu, 20% dropout and a max pooling function 2 x 2. Then again, we run the process described above by changing the kernel size to 128 then 258 with ReLu as an activation function, max pooling of 2x2 and 20% dropout. After that we flatten the 7 output to make it compatible with the next layers. Finally, we add one Dense layer (fully connected layer) with a softmax activation function giving the output size as 8. After that, we compiled the model using RMSprop optimizer with parameters like learning rate of 0.00005, momentum of 0.9 and epsilon with 1e-07 and loss function as sparse categorical crossentropy. Then we fit the model with train data and validation data using batch size of 16 and 200 epochs.

![cnn](https://user-images.githubusercontent.com/69428803/122646192-96e81580-d13b-11eb-8e98-4fd094548570.png)

# Support Vector Machine (SVM)
Support Vector Machine (SVM) is a supervised machine learning algorithm which can be used for both classification or regression challenges. However, it is mostly used in classification problems. In the SVM algorithm, we plot each data item as a point in n-dimensional space (where n is number of features you have) with the value of each feature being the value of a particular coordinate. Scaling can be done on data before applying in SVM classifier to avoid attributes in greater numeric ranges. Scaling can also be done to avoid some numerical difficulties during calculation.









