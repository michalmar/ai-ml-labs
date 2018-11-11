# AI Apps Hackathon
_guide to hack:_

## Overview
Create an intelligent application for image classification using AI service. Components:
- Object Clasification model - CustomVision.ai
- PowerApps application to call the object classification serivce and display results

## Prerequisitites 
- Microsoft Azure account
- Microsoft O365 account (PowerApps access)
- images to classification (at least 15 per category)

## Guide
### 1. CustomVision (https://cusomvision.ai)
1. create CustomVision project - classification
2. upload images
3. train
4. test

### 2. PowerApps (https://powerapps.microsoft.com)
1. create PowerApps application - phone layout
2. add elements: labels, media
3. add CustomVision as datasource [prediction key]
4. add media button action to score image (onselect, onchange):
5. update label property to update text based on results (text)
6. save & publish the app



