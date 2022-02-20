
# **Azure ML : Azure Test-Translation-API Description**

## **Overview**

Translator is a cloud-based neural machine translation service that is part of the Azure Cognitive Services family of REST APIs. Translator can be used with any operating system and powers many Microsoft products and services used by thousands of businesses worldwide to perform language translation and other language-related operations. In this overview, you'll learn how Translator can enable you to build intelligent, multi-language solutions for your applications across all supported languages.


## **Applications / Features**

The machine learning based API enables:

Translation - Cloud: Cloud translation is available in all languages for the Translate operation of Text Translation and for Document Translation.

Translation – Containers: Language support for Containers.

Custom Translator: Custom Translator can be used to create customized translation models which you can then use to customize your translated output while using the Text Translation or Document Translation features.

Auto Language Detection: Automatically detect the language of the source text while using Text Translation or Document Translation.

Dictionary: Use the Dictionary Lookup or Dictionary Examples operations from the Text Translation feature to display alternative translations from or to English and examples of words in context.

![](https://raw.githubusercontent.com/PrezSeah/galleryres/main/azure-machine-learning-APIs/azure-text-translation-API/cognitive-text-translation.png)

**Model Metadata**

Domain : Neural machine learning translation service

Application : Machine Learning

Industry : General

Input Data Format : Text

**Pricing**

Free - Standard Translation - 2M chars of any combination of standard translation and custom training free per month

Read full pricing details below

https://azure.microsoft.com/en-us/pricing/details/cognitive-services/translator/

**Documentation Link**

https://docs.microsoft.com/en-us/azure/cognitive-services/translator/translator-overview



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

