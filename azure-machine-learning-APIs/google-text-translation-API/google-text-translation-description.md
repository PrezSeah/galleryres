
# **Azure ML : Azure Test-Translation-API Description**

## **Overview**

Googletrans is a free and unlimited python library that implemented Google Translate API. This uses the Google Translate Ajax API to make calls to such methods as detect and translate.


## **Applications / Features**

-> Fast and reliable - it uses the same servers that translate.google.com uses
-> Auto language detection
-> Bulk translations
-> Customizable service URL
-> HTTP/2 support


-> The maximum character limit on a single text is 15k.
-> Due to limitations of the web version of google translate, this API does not guarantee that the library would work properly at all times (so please use this library if you don’t care about stability).
-> Important: If you want to use a stable API, I highly recommend you to use Google’s official translate API.
-> If you get HTTP 5xx error or errors like #6, it’s probably because Google has banned your client IP address.


## **Model Metadata**

Domain : Neural machine learning translation service

Application : Machine Learning

Industry : General

Input Data Format : Text


## **Documentation Link**

https://pypi.org/project/googletrans/

## Usage

#install googletrans using pip

!pip install googletrans

#Importing the necessary libraries

import pandas as pd

import googletrans

from googletrans import Translator


#Reading and storing the CSV file as a dataframe

df = pd.read_csv('/content/Vegetables_names_in_hindi.csv')

df.head(10)


translator = Translator()
translations = {}
for column in df.columns:
    # Unique elements of the column
    unique_elements = df[column].unique()
    for element in unique_elements:
        # Adding all the translations to a dictionary (translations)
        translations[element] = translator.translate(element).text
translations


#Replacing all the translated words from the dictionary to the original dataframe
df.replace(translations, inplace = True)
df.head(10)


