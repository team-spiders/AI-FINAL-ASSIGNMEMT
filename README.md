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


## dataset downloaded from kaggle 

![image](https://user-images.githubusercontent.com/115747921/205235183-1c97b52f-cdc4-4d4a-b993-8bf97cab78a9.png)

## Figure shows how UCF-101 datasets look after in training enviroment.

![image](https://user-images.githubusercontent.com/115747921/205235315-adf60828-934e-4f82-bba4-e79a5ee46f4c.png)

## Figure shows how videos are placed in each action class folder.

![image](https://user-images.githubusercontent.com/115747921/205235440-4cc3b3af-f095-4b2b-ad93-f66985b7c6a0.png)

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

Spatial-temporal features from “T” frames are extracted by using pre-trained CNN model. For our project we used DenseNet architecture.

![image](https://user-images.githubusercontent.com/115747921/205235972-82b31b6e-92cd-4a1d-9511-6850997bac31.png)

```
                            Video features extraction Pipeline
```
# Features Engineering

1) Because of limitation of hardware resources, we chose only 4 action classes among 110 action classes.

2) Since our model is based on supervised learning method, we labeled each action class as given table.

![image](https://user-images.githubusercontent.com/115747921/205236230-c591b675-d8fb-4378-80e6-87ad609c158b.png)

3) Input features and labeled are split to train, valid, and test dataset in 0.6:0.2:0.2 ratio.

# Action Recognition Model:Traditional approach 

Not long ago, LSTM/GRU was the model to do these kind of stuff. 

***Drawbacks of LSTM/GRU***

1) LSTM/GRU suffers from Vanishing Gradient Problem. So, RNN thus have short term memory and is not suitable of Inputs sequence is large.


2) LSTM/GRU  can’t process all the sequence Parallelly and can’t take advantage of modern GPU which are made to handle tasks parallely.


3) LSTM/GRU model is not good with transfers learning.


4) LSTMs take longer to train.


![image](https://user-images.githubusercontent.com/115747921/205236813-6e0a4dc5-ff53-483c-ad56-25cdda86462a.png)

## Our method : Transformer Encoder

![image](https://user-images.githubusercontent.com/115747921/205236893-d78e096c-2999-4511-8a0d-4359d795bc61.png)

## Transformer Encoder: Model Architecture

1) ***Positional Encoding***

- Describes the location or position of an entity in a sequence so that each position is assigned a unique representation.

![image](https://user-images.githubusercontent.com/115747921/205237104-535ca793-1870-43d7-9fe8-557b7cc775b3.png)

2) ***Multi-headed Attention***:

- Contains multiple self-attention layer within it.



- Gives more attention to important frames and less to non-important  frame.

![image](https://user-images.githubusercontent.com/115747921/205237553-40482e4b-4203-482a-8b60-42b73639f110.png)

3) ***Addition layer***:

- Similar to resnet, add the  input to the output from previous layer

![image](https://user-images.githubusercontent.com/115747921/205237887-440a1ab0-b90d-47f5-9cb6-7e706ff41f6d.png)

4) ***Feed forward Network***:

- Simplest form of neural network as information is only processed in one direction.



- Artificial neural network in which the connections between nodes does not form a cycle.

![image](https://user-images.githubusercontent.com/115747921/205238030-90a55d7b-8740-4b57-a3a8-2cacd344ce0a.png)

## Training pipeline

![image](https://user-images.githubusercontent.com/115747921/205238179-a86b9a94-4123-49ba-9b83-c372895edfdc.png)

## Advantages of Transformer over LSTM/GRU

- It process all the sequence at a same, thus taking the advantage of modern GPU.


- It doesn’t suffer from vanishing gradient and also good with transfer learning.


- Inspired from the success of BERT (a transformer model for language translation), we adopted BERT model for doing action recognition task.

## Experimental setup

![image](https://user-images.githubusercontent.com/115747921/205238390-15f0c310-20d3-4cdc-b539-04ff79ac7165.png)

## Weekly objectives

***Team meeting and discussion***

![image](https://user-images.githubusercontent.com/115747921/205239739-ad4c70ae-0e23-4507-aa9a-4f5c35c10e83.png)

![image](https://user-images.githubusercontent.com/115747921/205239805-13044475-046e-4dd4-87d2-630180d9052e.png)

![image](https://user-images.githubusercontent.com/115747921/205239838-d2c771c5-50a2-4b42-a6c7-fdc59e9507ac.png)

# Model evaluations

# Demo video and project implementation

## Contribution of team member

![image](https://user-images.githubusercontent.com/115747921/205240102-fb03ad00-22a1-4613-918c-d18af7119ada.png)









