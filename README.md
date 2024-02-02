# Speech Emotion Recognition
Speech emotion recognition of human using Multi-layer Perceptron classifier taking live audio speech

## Emotion Recognition From Speech
The understanding of emotions from voice by a human brain are normal instincts of human beings, but automating the process of emotion recognition from speech without referring any language or linguistic information remains an uphill grind. In the research work presented based on the input speech, I am trying to predict one of the six types of emotions (sad, neutral, happy, fear, angry, disgust). The diagram given below explain how emotion recognition from speech works. The audio features are extracted from input speech, then those features are passed to the emotion recognition model which predicts one of the six emotions for the given input speech.

## Motivation
Most of the smart devices or voice assistants or robots present in the world are not smart enough to understand the emotions. They are just like command and follow devices they have no emotional intelligence. When people are talking to each other based on the voice they understand situation and react to it, for instance if someone is angry then other person will try to clam him by conveying in soft tone, these kind of harmonic changes are not possible with smart devices or voice assistants as they lack emtional intelligence. So adding emotions and making devices understand emotions will take them one step further to human like intelligence.

## Dataset description

I have used two datasets and  datasets are freely available to downloaded from kaggle website. So I have downloaded the data, extracted and stored in my system.

    1. Ryerson Audio Visual Database of Emotional Speech and Song (Ravdess) dataset description:
        Dataset link to download: "https://www.kaggle.com/uwrfkaggler/ravdess-emotional-speech-audio"
        Dataset stored on my system at path: "C:\\Users\\GEETHA\\Desktop\\geetha_project\\ravdess_data\\"

        Dataset contains sub folders and file names as example in numbers format 03-01-01-01-01-01-01.wav.
        Actor (01 to 24. Odd numbered actors are male, even numbered actors are female).
        
        So based on the number there is a identifier for each number and its meaning are as follows:
        Modality (01 = full-AV, 02 = video-only, 03 = audio-only).
        Vocal channel (01 = speech, 02 = song).
        Emotion (01 = neutral, 02 = calm, 03 = happy, 04 = sad, 05 = angry, 06 = fearful, 07 = disgust, 08 = surprised).
        Emotional intensity (01 = normal, 02 = strong). NOTE: There is no strong intensity for the 'neutral' emotion.
        Statement (01 = "Kids are talking by the door", 02 = "Dogs are sitting by the door").
        Repetition (01 = 1st repetition, 02 = 2nd repetition).
        Therefore file 03-01-01-01-01-01-01.wav can be deduced as 03=audio-only, 01=speech, 01=neutral, 01=normal, 01=statement kids and 01=1st repetition.
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/835f1305-6625-4515-b4fa-ab8a875cce7b)

    2.Toronto emotional speech set (Tess) dataset description:
        Dataset link to download: "https://www.kaggle.com/ejlok1/toronto-emotional-speech-set-tess"
        Dataset stored on google drive at path: "C:\\Users\\GEETHA\\Desktop\\geetha_project\\TESS Toronto emotional␣speech set data\\"
        There are folders in format OAF_angry, OAF_neural, OAF_disgust, YAF_sad and so on, where name after the underscore of the folder name contains the emotion information, so the             name after the underscore of the folder name is taken and files residing insider the folders are labeled accordingly.

        
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/e328e405-5f89-44f9-9ec6-deee16b6fff9)

## Workflow of my project
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/e0a05e2e-b634-4741-9123-d1033af3f67b)


##  Import all required libraries
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/6109ebf6-ad32-4feb-8994-5a2dddf567e8)
## Load Datasets
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/9655ff32-6bec-47e3-87e2-8d26300d4a0b)


## Emotions in Dataset

![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/7cc46a0d-281c-443b-9941-dd996841f983)




 
## Extract emotion label from file path based on dataset naming convention
    def extract_emotion_label(file_path):
      if 'RAVDESS' in file_path.upper():
        emotion = emotions[file_path.split('\\')[-1].split('-')[2].split('.')[0]]
      elif 'TESS' in file_path.upper():
        emotion = file_path.split('\\')[-1].split('_')[2].split('.')[0]
      else:
        emotion = 'unknown'
      return emotion
      
## Function for extracting the features from Audio files.
  ![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/59d8d6e4-c9a5-47ba-8fed-5eb7e6a98f7b)

## Spilt dataset for training and testing 
  ![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/d46f5596-5e24-447c-a710-54f0a2b146bd)
## Count of training and testing audio files
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/503ca067-f427-4146-bacf-2b40b747d91c)

## Using MLP Classifier from Scikit-learn, build model and calculate the accuracy.
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/fa5fff4b-ef25-4202-9b8b-57f85d5000ec)
## Record live audio from microphone to know the emotion of current spoken audio
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/53001faf-c3e8-44f4-a896-9e5211c393ba)
## prediction emotion for exsiting audio.
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/c56927ed-395f-4a23-b642-f2c3240d91cf)
## User Interface of my Project
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/b6786491-adb2-44d2-8bbf-49fda0af3d8d)                     
![image](https://github.com/geethaseshapu/speech-emption-recognition/assets/141820992/56d6af8c-179a-4318-a2ae-ede24fa18462)


 

