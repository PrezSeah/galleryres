
# **Azure ML : Azure Test-Translation-API Testing**

## **Testing Link**

The testing of Anomaly Detection API can be done using multiple programming languages including  C#, Python, Java The complete testing documentation can be accessed using the link :

https://docs.microsoft.com/en-us/azure/cognitive-services/translator/quickstart-translator?tabs=python

## **Prerequisites**

-> Azure subscription - Create one for free

-> Once you have an Azure subscription, create a Translator resource in the Azure portal to get your key and endpoint. After it deploys, select Go to resource.

-> You'll need the key and endpoint from the resource to connect your application to the Translator service. You'll paste your key and endpoint into the code below later in the quickstart. You can find these values on the Azure portal Keys and Endpoint page.

-> You can use the free pricing tier (F0) to try the service, and upgrade later to a paid tier for production.


## **Setting Up**

## Translate text

import requests, uuid, json

#Add your subscription key and endpoint
subscription_key = "YOUR_SUBSCRIPTION_KEY"
endpoint = "https://api.cognitive.microsofttranslator.com"

#Add your location, also known as region. The default is global.
#This is required if using a Cognitive Services resource.
location = "YOUR_RESOURCE_LOCATION"

path = '/translate'
constructed_url = endpoint + path

params = {
    'api-version': '3.0',
    'from': 'en',
    'to': ['de', 'it']
}

headers = {
    'Ocp-Apim-Subscription-Key': subscription_key,
    'Ocp-Apim-Subscription-Region': location,
    'Content-type': 'application/json',
    'X-ClientTraceId': str(uuid.uuid4())
}

#You can pass more than one object in body.
body = [{
    'text': 'Hello World!'
}]

request = requests.post(constructed_url, params=params, headers=headers, json=body)
response = request.json()

print(json.dumps(response, sort_keys=True, ensure_ascii=False, indent=4, separators=(',', ': ')))

## Detect source language during translation
import requests, uuid, json

#Add your subscription key and endpoint
subscription_key = "YOUR_SUBSCRIPTION_KEY"
endpoint = "https://api.cognitive.microsofttranslator.com"

#Add your location, also known as region. The default is global.
#This is required if using a Cognitive Services resource.
location = "YOUR_RESOURCE_LOCATION"

path = '/translate'
constructed_url = endpoint + path

params = {
    'api-version': '3.0',
    'to': ['de', 'it']
}

headers = {
    'Ocp-Apim-Subscription-Key': subscription_key,
    'Ocp-Apim-Subscription-Region': location,
    'Content-type': 'application/json',
    'X-ClientTraceId': str(uuid.uuid4())
}

#You can pass more than one object in body.
body = [{
    'text': 'Hello World!'
}]

request = requests.post(constructed_url, params=params, headers=headers, json=body)
response = request.json()

print(json.dumps(response, sort_keys=True, ensure_ascii=False, indent=4, separators=(',', ': ')))


## Transliterate during translation

import requests, uuid, json

#Add your subscription key and endpoint
subscription_key = "YOUR_SUBSCRIPTION_KEY"
endpoint = "https://api.cognitive.microsofttranslator.com"

#Add your location, also known as region. The default is global.
#This is required if using a Cognitive Services resource.
location = "YOUR_RESOURCE_LOCATION"

path = '/translate'
constructed_url = endpoint + path

params = {
    'api-version': '3.0',
    'to': 'th',
    'toScript': 'latn'
}

headers = {
    'Ocp-Apim-Subscription-Key': subscription_key,
    'Ocp-Apim-Subscription-Region': location,
    'Content-type': 'application/json',
    'X-ClientTraceId': str(uuid.uuid4())
}

#You can pass more than one object in body.
body = [{
    'text': 'Hello'
}]
request = requests.post(constructed_url, params=params, headers=headers, json=body)
response = request.json()

print(json.dumps(response, sort_keys=True, ensure_ascii=False, indent=4, separators=(',', ': ')))
