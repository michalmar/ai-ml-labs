# AI Apps Hackathon
_guide to hack:_

## Overview
Create an intelligent application for image classification using AI service. Components:
- Object Clasification model - CustomVision.ai
- PowerApps application to call the object classification serivce and display results

![alt text](./assets/powerapps.png "Logo PowerApps")
![alt text](./assets/customvision.png "Logo CustomVision")

## Prerequisitites 
- Microsoft Azure account
- Microsoft O365 account (PowerApps access)
- images to classification (at least 15 per category)

## Guide
### 1. CustomVision (https://cusomvision.ai)
1. create CustomVision project - classification
![alt text](./assets/create_project.jpg "create_project")
2. upload images
3. train
![alt text](./assets/train.jpg "train")
4. test
![alt text](./assets/test.jpg "test")

### 2. PowerApps (https://powerapps.microsoft.com)
1. create PowerApps application - phone layout
![alt text](./assets/app1.jpg "app")
2. add elements: labels, media
![alt text](./assets/app_layout.jpg "app")
3. add CustomVision as datasource [prediction key]
![alt text](./assets/app_datasource.jpg "app")
4. add media button action to score image (onselect, onchange): `UpdateContext({res:CustomVision.PredictImage("xxxxxxxx-xxxx-xxx-xxxx-xxxxxx", UploadedImage1).Predictions});
UpdateContext({vis:true})`
5. update label property to update text based on results (text): `Concatenate("Probability: ",Text(First(res).Probability)) //If(First(res).Tag="superb" && First(res).Probability>0.8,"Yes", "NO")`
6. save & publish the app



