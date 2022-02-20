
**Azure ML : Anomaly Detection Description**

**Overview**

Anomaly Detection is an API built with Azure Machine Learning that is useful for detecting different types of anomalous patterns in your time series data. The API assigns an anomaly score to each data point in the time series, which can be used for generating alerts, monitoring through dashboards or connecting with your ticketing systems.

The [Anomaly Detection API](https://docs.microsoft.com/en-us/azure/machine-learning/machine-learning-apps-anomaly-detection-api) can detect the following types of anomalies on time series data:

*   _Spikes and Dips:_ For example, when monitoring the number of login failures to a service or number of checkouts in an e-commerce site, unusual spikes or dips could indicate security attacks or service disruptions.
*   _Positive and negative trends:_ When monitoring memory usage in computing, for instance, shrinking free memory size is indicative of a potential memory leak; when monitoring service queue length, a persistent upward trend may indicate an underlying software issue.
*   _Level changes and changes in dynamic range of values:_ For example, level changes in latencies of a service after a service upgrade or lower levels of exceptions after upgrade can be interesting to monitor.

**Applications / Features**

The machine learning based API enables:

*   _Flexible and robust detection:_ The anomaly detection models allow users to configure sensitivity settings and detect anomalies among seasonal and non-seasonal data sets. Users can adjust the anomaly detection model to make the detection API less or more sensitive according to their needs. This would mean detecting the less or more visible anomalies in data with and without seasonal patterns. 
*   _Scalable and timely detection:_ The traditional way of monitoring with preset thresholds set by experts' domain knowledge are costly and not scalable to millions of dynamically changing data sets. The anomaly detection models in this API are learned and models are tuned automatically from both historical and real-time data.
*   _Proactive and actionable detection:_ Slow trend and level change detection can be applied for early anomaly detection. The early abnormal signals detected can be used to direct humans to investigate and act on the problem areas.  In addition, root cause analysis models and alerting tools can be developed on top of this anomaly detection API service.

![](https://raw.githubusercontent.com/PrezSeah/galleryres/main/azure-machine-learning-APIs/anomaly-detection-API/azureml-anomaly-detection-description_files/image001.jpg)

**Model Metadata**

Domain : Machine Learning

Application : Machine Learning

Industry : General

Input Data Format : Seasonal and Non Seasonal Datasets

**Pricing**

Instance

Features

Price

Free - Web/Container

Univariate anomaly detection

20000 transactions free per month

Standard - Web/Container

 Univariate anomaly detection

 Multivariate anomaly detection

 $0.314 per 1,000 transactions

 Free

https://azure.microsoft.com/en-us/pricing/details/cognitive-services/anomaly-detector/

**Deployment Link**

[https://portal.azure.com/#create/Microsoft.CognitiveServicesAnomalyDetector](https://portal.azure.com/#create/Microsoft.CognitiveServicesAnomalyDetector)

**Documentation Link**

[https://docs.microsoft.com/en-us/azure/cognitive-services/anomaly-detector/](https://docs.microsoft.com/en-us/azure/cognitive-services/anomaly-detector/)



**Azure ML : Anomaly Detection - Testing**

**Testing Link**

The testing of Anomaly Detection API can be done using multiple programming languages including  C#, Python, Java  The complete testing documentation can be accessed using the link :

[https://docs.microsoft.com/en-us/azure/cognitive-services/anomaly-detector/quickstarts/client-libraries?tabs=windows&pivots=programming-language-python](https://docs.microsoft.com/en-us/azure/cognitive-services/anomaly-detector/quickstarts/client-libraries?tabs=windows&pivots=programming-language-python)

**Deployment Link**

[https://portal.azure.com/#create/Microsoft.CognitiveServicesAnomalyDetector](https://portal.azure.com/#create/Microsoft.CognitiveServicesAnomalyDetector)

**Prerequisites**

*   Azure subscription - [Create one for free](https://azure.microsoft.com/free/cognitive-services/)

Python 3.x

*   Your Azure account must have a Cognitive Services Contributor role assigned in order for you to agree to the responsible AI terms and create a resource. Contact your administrator to get this role assigned to your account.
*   Once you have your Azure subscription, [create an Anomaly Detector resource](https://ms.portal.azure.com/#create/Microsoft.CognitiveServicesAnomalyDetector "Create an Anomaly Detector resource") in the Azure portal to get your key and endpoint. Wait for it to deploy and click the **Go to resource** button.

*   You will need the key and endpoint from the resource you create to connect your application to the Anomaly Detector API. You'll paste your key and endpoint into the code below later in the quickstart. You can use the free pricing tier (F0) to try the service, and upgrade later to a paid tier for production.

**Setting Up**

**Install the client library**

After installing Python, you can install the client library with:

pip install --upgrade azure-ai-anomalydetector

**Create a new Python application**

import os

from azure.ai.anomalydetector import AnomalyDetectorClient

from azure.ai.anomalydetector.models import DetectRequest, TimeSeriesPoint, TimeGranularity, \\

 AnomalyDetectorError

from azure.core.credentials import AzureKeyCredential

import pandas as pd 

SUBSCRIPTION\_KEY = os.environ\["ANOMALY\_DETECTOR\_KEY"\]

ANOMALY\_DETECTOR\_ENDPOINT = os.environ\["ANOMALY\_DETECTOR\_ENDPOINT"\]

TIME\_SERIES\_DATA\_PATH = os.path.join("./sample\_data", "request-data.csv") 

**Authenticate the client**
---------------------------

\# Create an authenticated FaceClient.

client = AnomalyDetectorClient(AzureKeyCredential(SUBSCRIPTION\_KEY), ANOMALY\_DETECTOR\_ENDPOINT)

**Load time series data from a file**
-------------------------------------

series = \[\]

data\_file = pd.read\_csv(TIME\_SERIES\_DATA\_PATH, header=None, encoding='utf-8', parse\_dates\=\[0\])

for index, row in data\_file.iterrows():

 series.append(TimeSeriesPoint(timestamp=row\[0\], value=row\[1\]))

request = DetectRequest(series=series, granularity=TimeGranularity.daily)

**Detect anomalies in the entire data set**
-------------------------------------------

print('Detecting anomalies in the entire time series.')

try:

response = client.detect\_entire\_series(request)

except AnomalyDetectorError as e:

 print('Error code: {}'.format(e.error.code), 'Error message: {}'.format(e.error.message))

except Exception as e:

 print(e)

if any(response.is\_anomaly):

 print('An anomaly was detected at index:')

 for i, value in enumerate(response.is\_anomaly):

 if value:

 print(i)

else:

 print('No anomalies were detected in the time series.')


