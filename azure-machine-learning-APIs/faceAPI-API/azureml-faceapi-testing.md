
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

 ![](https://raw.githubusercontent.com/PrezSeah/galleryres/main/azure-machine-learning-APIs/faceAPI-API/azureml-faceapi-testing_files/image003.png)

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
