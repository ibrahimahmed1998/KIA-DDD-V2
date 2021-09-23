# J6_Hackathon_KIA_DDD
DDD refers to the detection of driver drowsiness.\
As we know that there are a lot of car accidents due to drowsiness of the driver while driving. [Source](https://www.nsc.org/road/safety-topics/fatigued-driver).\
We also know the progress of science in creating self-driving cars to reduce the rate of those accidents,\
but the average cost of self-driving cars is $30,000 [Source](https://www.forbes.com/sites/uhenergy/2019/05/21/self-driving-automobiles-how-soon-and-how-much/?sh=2f7d9e2638bd), and as we know this is a high price.\
And here comes our role to solve this problem in a smart and low-cost way.

# The Team
- Team Leader : Kareem Gamal Mahmoud      (ASU, CS)
- Team Member 1 : Ahmed Mohamed Gaber     (ASU, CS)
- Team Member 2 : Ibrahim Ahmed Ibrahim   (ASU, CS)
![This is our image](https://user-images.githubusercontent.com/51359449/134501329-ff63c741-9a4d-4d4a-906a-a4841ad623d9.jpeg)

# Toy Project
## Problem Statement
DDD is a software program that works to identify driver violations while driving,\
such as drowsiness, not paying attention to the road or talking to the phone directly.\
This project is intended to focus on being used by public transport drivers on highways,
bus drivers, and truck drivers, as well as regular cars.

## Learning Process
We were very interested in the field of artificial intelligence, specifically the field of machine learning.\
And we start the road map with  [Andrew's courses](https://www.coursera.org/specializations/deep-learning) and [Hisham Assem’s courses](https://www.youtube.com/channel/UCxxljM6JkSvJVSD_T90ZnMw)\
And actually we wanted to build a binary classification model using CNN,\
But it wasn't easy for us to deal with some of the problems we had faced with the OpenCV model for human face detection.\
So, we decided to change this model with Dlib framework which has better accuracy and finally we are stable with Mediapipe framework.

# Coding Competition
## Problem Statement
Driver’s inattention might be the result of a lack of alertness when driving due to driver drowsiness and distraction.\
Unlike driver distraction, driver drowsiness involves no triggering event but, instead, is characterized by a progressive withdrawal of attention from the road and traffic demands.\
Both driver drowsiness and distraction, however, might have the same effects, that is decreased driving performance, longer reaction time, and an increased risk of crash involvement. 

## Solution
- Based on acquisition of video from the camera that is in front of driver perform real-time processing of an incoming video stream in order to infer the driver’s level of fatigue if the drowsiness is estimated then it will give the alert by sensing the eyes.
- Mediapipe framework : which is an open source framework created by google and it has a lot of module for computer vision problems.
- Django framework : which is also an open source backend framework that allow us to present our models in efficient way.
![example_1](https://user-images.githubusercontent.com/51359449/134506521-d3541fd9-42ce-4b63-b654-c4e28e93b263.PNG)

## Methodology
### Pose Classification Model
![pose_tracking_full_body_landmarks](https://user-images.githubusercontent.com/51359449/134508516-cfa33088-e44a-467f-9877-19b6a23cec43.png)
- In the pose classification model we check for two violations
 1. The first violation is to check whether the landmark (13) is above the landmark (11) or not, as well as checking whether the landmark (16) is above the landmark (12) or not.\ In this clever way we can detect if the driver has increased their blind spots or not and with this we don't need an object detection model to detect if there is a phone or not because in real life it allows you as a driver to use your phone while driving via a phone stand
![banner20210118_f150iphone4_mobile-530_500](https://user-images.githubusercontent.com/51359449/134511569-c6753ef4-f70e-45f6-a0a8-83641c9e989e.jpg)


  2. The second violation is to get the distance between lanmark (7) and (0) and the distance between the landmark (8) and (0).\ And comparing it with knowing if the distance(7,0) is longer than the distance(8,0), we conclude that the driver is looking to the right and if else we conclude that the driver is looking to the other way. 

### Holistic Model 
- In the Holistic Model we check if the driver is sleepy or not by get a ratio between from calculate the distance of eye landmarks.
- to learn more about how it goes please visit this [Site](https://www.pyimagesearch.com/2017/05/08/drowsiness-detection-opencv/)
![brfv5_landmarks](https://user-images.githubusercontent.com/51359449/134513452-f6c82843-59c2-4e31-b107-ed00263462ae.jpg)

### Hands Detection Models
- we use this model to detect the first and the second finger for voice documentation and gesture volume control ,respectively.
- Note: If you watch the demo video, you will not notice that the sound goes down and up because this is recorded from the computer speakers and not through an external microphone. I mean it works fine when you test the project in real life.
![hand_landmarks](https://user-images.githubusercontent.com/51359449/134514877-258e9ac3-ef74-42ac-9a57-c4784385ac0c.png)


## System Architecture proposal
- We used our local hardware resources (our laptops) and get the input image through laptop camera or mobile phone camera,\ But in the real life of course we will need a hardware platform like ( raspberry pi ) but acully we are not a hardware team we are a software team but that is interisting for us to study IOT field.
![webcam-android-couvertur-min (1)](https://user-images.githubusercontent.com/51359449/134518387-dbec727e-db5e-4966-bbb9-8dedccb7e75c.png)

## Some Bad news :(
 - We were looking for get the location of the driver when he/she makes any mistake to put some rest places on that road or something like that,  but unfortunately it is a paid services from google maps. So, it is not work for now.
 - We came to implement a database, but time did not help us.

## Demo Video
- [Link](https://drive.google.com/file/d/1PHd-iDXBjbQ7lbhOhCcyyV0WJcLVOK7E/view?usp=sharing) 

## Steps to run the software
- First you need to install python 3.8.6 [(Link)](https://www.python.org/downloads/)
- After that install mediapipe [(Link)](https://google.github.io/mediapipe/getting_started/python.html)
- Then install Django framwork [(Link)](https://docs.djangoproject.com/en/3.2/topics/install/)
- Finally install this requirements.txt file which include the libraries of our environment. [(Link)](https://intellipaat.com/community/31672/how-to-use-requirements-txt-to-install-all-dependencies-in-a-python-project)
- Enjoy :)
