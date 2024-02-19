# Emotion Based Music Recommendation
CNN model to reccomend music based on user facial emotion using FER 2013 dataset and Spotipy api



# Project Description:
The FER 2013 dataset is used to train the emotion recognition model. It is capable of identifying seven emotions. The project uses a webcam to provide a live video feed, which is then fed through an algorithm to predict a mood. The app will then use the spotipy wrapper to retrieve a playlist of songs from Spotify based on the expected emotion and recommend songs by presenting them on the screen.

# Features:
- Real time expression detection and song recommendations.
- Playlists fetched from Spotipy API.

# Running the app:
Flask: 
- Run <code>pip install -r requirements.txt</code> to install all dependencies.
- In Spotipy.py enter your credentials generated by your Spotify Developer account in 'auth_manager'. 
- Run <code>python app.py</code> and give camera permission if asked.

# Tech Stack:
- Keras
- Tensorflow
- Spotipy
- Flask

# Dataset:
The well-known FER2013 dataset served as the basis for this project. Using this information, models can identify seven different emotions.The dataset can be found <a href = "https://www.kaggle.com/msambare/fer2013">here</a>.

The dataset is noticeably unbalanced, with the happy class having the highest representation. This could be an explanation to the average accuracy after training.

# Model Architecture:
- The model architecture is a sequential model consisting of Conv2d, Maxpool2d, Dropout and Dense layers:
1. Conv2D layers throughout the model have different filter size from 32 to 128, all with activation 'relu'
2. Pooling layers have pool size (2,2)
3. Dropout is set to 0.25 as anything above results in poor performance
4. Final Dense layer has 'softmax' activation for classifying 7 emotions
- Used 'categorical_crossentropy' for loss with 'Adam' optimizer with 'accuracy' metric



# Image Processing and Training:
- The 'ImageDataGenerator' feature in the Keras API was utilized to normalize, resize the photos to (48,48), and convert them to grayscale in batches of 64..
- Training took around 13 hours locally for 75 epochs with an accuracy of ~66 %

# Current condition:
The project functions flawlessly as a whole. Because live detection uses multithreading, it provides good frame rates.

# Project Components:
- Spotipy is a module that uses the Spotipy wrapper to connect to Spotify and obtain songs..
- haarcascade is for face detection.
- camera.py is the module for video streaming, frame capturing, prediction and recommendation which are passed to main.py.
- main.py is the main flask application file.
- index.html in 'templates' directory is the web page for the application. Basic HTML and CSS.
- utils.py is an utility module for video streaming of web camera with threads to enable real time detection.
- train.py is the script for image processing and training the model.

