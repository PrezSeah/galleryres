# Machine Learning Web Service With Power Apps Using Power Automate

## Deploy Machine learning model 

Perfoming below steps to create and deploy Machine learning model.

* Data Gathering
* Data Cleaning and Preprocessing
* Training Data Model
* Scoring Data Model
* Evaluating Data Model
  
## Integrate Azure ML Studio with Power Apps.

### Power Apps 
It is platform as services. It allows you to create Mobile Apps that run on Android, iOS, Windows (Modern Apps) — and with almost any Internet browser. You can act and modify data with PowerApps

### Setting up and Deploying Web Service
* Open your training experiment 
* On the bottom of page select Set up Web Service and choose Predictive Web Service (Recommended) from it.
* It will create a Predictive Experiment just like below.
  
![Predictive Experiment](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/PredictiveExperiment.JPG)  

* This will create input and output schema for our Web Service.
*  Now Deploy it by selecting Deploy Web Service in the bottom.(You need to run your predictive experiment before deploying it.)
*  After deployment, it is going to redirect you to an API dashboard.
![API Dashboard](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/APIDashboard.JPG) 

*  Now you can Test your model from the TEST button by entering some set of values and it will predict the income


## Create a flow in Power Automate
* Create a new flow using PowerApps button template.
![Template](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/PowerApps.JPG) 
* Add HTTP action. For completing this action you need to go to API dashboard.
  * Method: POST
  * URI: On API dashboard, click Request/Response. This will open API documentation page. Copy Request URI and paste it here.
  * Headers: Copy all Request Headers and paste it in here.(You can find API Key on API Dashboard)
  * Body: Copy Request Body and paste it here. Now in this step you need to replace requested “Values” with your own input values.
  
  ![Http Request](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/HttpReqeust.JPG) 

  ![Http Request](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/HttpRequest2.JPG) 
* Now add Parse JSON action to parse the response from our API call in JSON format.
  * Content: Add Body variable.
  * Schema: Select Generate from Sample and paste your Response body from API Documentation page.
  
 ![Sample Json](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SampleJson.JPG) 
* Add Respond to PowerApp or flow action. Choose Text as the type of output. For the value field, we need to retrieve our income variable through an expression. It would be something like 
  
 ![PowerApp](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/PowerAPPSFlow.JPG) 
  
### Create a Canvas app in PowerApps
* Create a blank canvas app and create its structure somehow like in the below image using Labels, Text Inputs and Button.
* First go to Action and choose Power Automate. You will see the lists of flows associated with PowerApps. You need to add your flow.
  
![Connection](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/PowerAppsIntration.JPG) 
* Now OnSelect of Predict Button write the following query:
  
![Integration](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/PowerAppsUI.JPG) 
* Now select Label to show our output income. Add the following query on Text property of Label.
* 
![Collection](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/ResponseCol.JPG) 
* Now you can customize your PowerApps on your own. I have shown the prediction in next screen like below.
  
![Response](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/ResponseScreen.JPG) 

### References and further reading:
* https://www.avepoint.com/blog/office-365/microsoft-powerapps/
* https://tallyfy.com/what-is-microsoft-flow-power-automate/
* https://centricconsulting.com/blog/
* https://medium.com/analytics-vidhya/integrate-azure-ml-studio-with-powerapps-and-power-automate-part-1-c201dbce2bc6
* https://medium.com/@sahilsrivastava94/integrate-azure-ml-studio-with-powerapps-and-power-automate-part-2-b556093aeb9f