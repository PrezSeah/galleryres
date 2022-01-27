
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

