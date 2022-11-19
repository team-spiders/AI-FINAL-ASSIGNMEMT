# Transformer based Human behaviour Analysis

## TEAM MEMBERS
```
Team leader :                     Other members:
Akash Ghimire (12194814)         Sanjib Tamang (12194939)
                                 Ritik Deuja (12194824)
                                 Keshav Adhikari (12194874)
 ```
 
## what is human action recognition ?

It is the task of identifying action of a person in an image or video of performing a certain activity . 
Trained to identify a wide range of behaviors, like  drinking, falling, and riding a bike to running and sleeping.
Collects human behaviour from videos pixel by pixel and analyzes them using comprehensive and advanced algorithms.
Detect, analyze and interpret activity in real time by employing AI.

## ***Methodology*** 

## Dataset Used: ( UCF 101 Action Recognition Dataset )

An action recognition data set of realistic action videos, collected from YouTube.
```
Number of Action Classes: 101
Trimmed Video Dataset 
Action categories can be divided into five types: 
Human-Object Interaction, Body-Motion Only,
Human-Human Interaction,Playing Musical Instruments,and Sports.
One of the most popular public action recognition dataset
```

![image](https://user-images.githubusercontent.com/115747921/202713846-72bb1f5b-2bb7-45f3-b767-ec6d143a78ba.png)

# Sample  video 
https://user-images.githubusercontent.com/115747921/202716112-8cc407c9-9b1a-4ca7-9813-5e6782d94a21.mp4

```
                    action class
```

## Features Extraction 

Spatial-temporal features from “T” frames are extracted by using pre-trained CNN model. For our project we used DenseNet architecture. 

![image](https://user-images.githubusercontent.com/115747921/202716765-27400efa-7de7-4af0-9e09-09ee3ffd37db.png)

## Architecture of DenseNet

![image](https://user-images.githubusercontent.com/115747921/202717216-d1a877eb-7831-4762-910c-1cb67c2aac89.png)

## Dataset Preprocessing
Before understanding Dataset Preprocessing, let us understand some terminology. 

1. ***Spatial Information***:
Information obtain from single Image. Example: For image analysis, DNN utilizes spatial information from image to classify an  image into some class.

2. ***Temporal Information***:
Information obtain over a period of time or event. For example, RNN utilizes text information over a period of sequence to do language translation.

Since video are collection of images within a period of time we need Spatial-temporal information.
Each video are uniformly sampled into T number of frames.

![image](https://user-images.githubusercontent.com/115747921/202822439-64388b17-2c5a-446f-8ff5-e48b630f8833.png)



