
**Azure ML : Face API Description**

**Overview**

Face APIs provide state-of-the-art algorithms to process face images, like face detection with gender and age prediction, recognition, alignment and other application level features.The Azure Face service provides AI algorithms that detect, recognize, and analyze human faces in images. Facial recognition software is important in many different scenarios, such as identity verification, touchless access control, and face blurring for privacy.

**Applications / Features**

Face detection with attributes extraction

You will get the detected faces with rectangles indicating the face positions and a series of face related attributes, include landmarks, pose, gender and age by giving an image.

![](https://raw.githubusercontent.com/PrezSeah/galleryres/main/azure-machine-learning-APIs/faceAPI-API/azureml-faceapi-description_files/image001.png)

Face Verification
-----------------

Given two detected faces, you will get result indicates whether the two requested faces belong to the same person.

![](https://raw.githubusercontent.com/PrezSeah/galleryres/main/azure-machine-learning-APIs/faceAPI-API/azureml-faceapi-description_files/image002.png)

Face Grouping
-------------

Provide service a set of unknown faces, it will automatically divide them into several groups based on similarity:

![](https://raw.githubusercontent.com/PrezSeah/galleryres/main/azure-machine-learning-APIs/faceAPI-API/azureml-faceapi-description_files/image003.png)

Face Identification
-------------------

You can use Face Identification to recognize persons' identities.

![](https://raw.githubusercontent.com/PrezSeah/galleryres/main/azure-machine-learning-APIs/faceAPI-API/azureml-faceapi-description_files/image004.png)

**Model Metadata**

Domain : Vision

Application : Face Tagging

Industry : General

Input Data Format : Image

**API Demo Link**

  

[https://azure.microsoft.com/en-us/services/cognitive-services/face/#demo](https://azure.microsoft.com/en-us/services/cognitive-services/face/#demo)

**Pricing**

Instance

Transaction Per Second

Features

Price

Free - Web/Container

20 transactions per minute

Face Detection  
Face Verification  
Face Identification  
Face Grouping  
Similar Face Search

30,000 transactions free per month

Standard - Web/Container

10 TPS

Face Detection  
Face Verification  
Face Identification  
Face Grouping  
Similar Face Search

0-1M transactions -$1 per 1,000 transactions1-5M transactions - $0.80 per 1,000 transactions5-100M transactions - $0.60 per 1,000 transactions100M+ transactions -$0.40 per 1,000 transactions

https://azure.microsoft.com/en-us/pricing/details/cognitive-services/face-api/

**Deployment Link**

[https://portal.azure.com/#create/Microsoft.CognitiveServicesFace](https://portal.azure.com/#create/Microsoft.CognitiveServicesFace)

**Documentation Link**

[https://docs.microsoft.com/en-us/azure/cognitive-services/face/overview](https://docs.microsoft.com/en-us/azure/cognitive-services/face/overview)


**Azure ML : Face API - Testing**

**Testing Link**

The testing of Face API can be done using multiple programming languages including C#, Python, Java The complete testing documentation can be accessed using the link :

[https://docs.microsoft.com/en-us/azure/cognitive-services/face/quickstarts/client-libraries?tabs=visual-studio&pivots=programming-language-python](https://docs.microsoft.com/en-us/azure/cognitive-services/face/quickstarts/client-libraries?tabs=visual-studio&pivots=programming-language-python)

**Deployment Link**

[https://portal.azure.com/#create/Microsoft.CognitiveServicesFace](https://portal.azure.com/#create/Microsoft.CognitiveServicesFace)

**Prerequisites**

*   Azure subscription - [Create one for free](https://azure.microsoft.com/free/cognitive-services/)

 Python 3.x

*   Your Azure account must have a Cognitive Services Contributor role assigned in order for you to agree to the responsible AI terms and create a resource. Contact your administrator to get this role assigned to your account.

 Once you have your Azure subscription, [create a Face resource](https://portal.azure.com/#create/Microsoft.CognitiveServicesFace "Create a Face resource") in the Azure portal to get your key and endpoint. After it deploys, click **Go to resource**.

*   You will need the key and endpoint from the resource you create to connect your application to the Face API. You'll paste your key and endpoint into the code below later in the quickstart.

**Setting Up**

**Install the client library**

After installing Python, you can install the client library with:

pip install --upgrade azure-cognitiveservices\-vision-face

**Create a new Python application**

import asyncio

import io

import glob

import os

import sys

import time

import uuid

import requests

from urllib.parse import urlparse

from io import BytesIO

\# To install this module, run:

\# python -m pip install Pillow

from PIL import Image, ImageDraw

from azure.cognitiveservices.vision.face import FaceClient

from msrest.authentication import CognitiveServicesCredentials

from azure.cognitiveservices.vision.face.models import TrainingStatusType, Person

Then, create variables for your resource's Azure endpoint and key.

\# This key will serve all examples in this document.

KEY = "PASTE\_YOUR\_FACE\_SUBSCRIPTION\_KEY\_HERE"

\# This endpoint will be used in all examples in this quickstart.

ENDPOINT = "PASTE\_YOUR\_FACE\_ENDPOINT\_HERE"

**Authenticate the client**
---------------------------

\# Create an authenticated FaceClient.

face\_client = FaceClient(ENDPOINT, CognitiveServicesCredentials(KEY))

### Display and frame faces

\# Detect a face in an image that contains a single face

single\_face\_image\_url = 'https://raw.githubusercontent.com/Microsoft/Cognitive-Face-Windows/master/Data/detection1.jpg'

single\_image\_name = os.path.basename(single\_face\_image\_url)

\# We use detection model 3 to get better performance.

detected\_faces = face\_client.face.detect\_with\_url(url\=single\_face\_image\_url, detection\_model\='detection\_03')

if not detected\_faces:

raise Exception('No face detected from image {}'.format(single\_image\_name))

\# Convert width height to a point in a rectangle

def getRectangle(faceDictionary):

rect = faceDictionary.face\_rectangle

left = rect.left

top = rect.top

right = left + rect.width

bottom = top + rect.height



return ((left, top), (right, bottom))

def drawFaceRectangles() :

\# Download the image from the url

response = requests.get(single\_face\_image\_url)

img = Image.open(BytesIO(response.content))

\# For each face returned use the face rectangle and draw a red box.

print('Drawing rectangle around face... see popup for results.')

 draw = ImageDraw.Draw(img)

for face in detected\_faces:

 draw.rectangle(getRectangle(face), outline='red')

\# Display the image in the default image browser.

img.show()

\# Uncomment this to show the face rectangles.

# drawFaceRectangles() 

 **Sample Output**

 ![](https://raw.githubusercontent.com/PrezSeah/galleryres/main/azure-machine-learning-APIs/faceAPI-API/azureml-faceapi-testing_files/image001.png)

**Other Applications**

**Name**

**Description**

[FaceClient](https://docs.microsoft.com/en-us/python/api/azure-cognitiveservices-vision-face/azure.cognitiveservices.vision.face.faceclient)

This class represents your authorization to use the Face service, and you need it for all Face functionality. You instantiate it with your subscription information, and you use it to produce instances of other classes.

[FaceOperations](https://docs.microsoft.com/en-us/python/api/azure-cognitiveservices-vision-face/azure.cognitiveservices.vision.face.operations.faceoperations)

This class handles the basic detection and recognition tasks that you can do with human faces.

[DetectedFace](https://docs.microsoft.com/en-us/python/api/azure-cognitiveservices-vision-face/azure.cognitiveservices.vision.face.models.detectedface)

This class represents all of the data that was detected from a single face in an image. You can use it to retrieve detailed information about the face.

[FaceListOperations](https://docs.microsoft.com/en-us/python/api/azure-cognitiveservices-vision-face/azure.cognitiveservices.vision.face.operations.facelistoperations)

This class manages the cloud-stored **FaceList** constructs, which store an assorted set of faces.

[PersonGroupPersonOperations](https://docs.microsoft.com/en-us/python/api/azure-cognitiveservices-vision-face/azure.cognitiveservices.vision.face.operations.persongrouppersonoperations)

This class manages the cloud-stored **Person** constructs, which store a set of faces that belong to a single person.

[PersonGroupOperations](https://docs.microsoft.com/en-us/python/api/azure-cognitiveservices-vision-face/azure.cognitiveservices.vision.face.operations.persongroupoperations)

This class manages the cloud-stored **PersonGroup** constructs, which store a set of assorted **Person** objects.

[ShapshotOperations](https://docs.microsoft.com/en-us/python/api/azure-cognitiveservices-vision-face/azure.cognitiveservices.vision.face.operations.snapshotoperations)

This class manages the Snapshot functionality; you can use it to temporarily save all of your cloud-based face data and migrate that data to a new Azure subscription.

