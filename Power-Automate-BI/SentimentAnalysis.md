# Sentiment Analysis Using Power Automate

Text Analysis that identify and extract subjective information to help business in understanding the sentiment of their product or serivices while communicating with the customers.
It is easy with AI builder of Power Automate to get Positive or negative sentiment of text.
* Create solution/flow in Power Automate
* Login to Power Automate and click the solutions from the left navigation.
* Create a new solution from the top navigation.
* Give the name of solution, select the publisher name of create new publisher.
* Give the version number. Default is 1.0.0.0 because it is a new solution.
* Once the solution is created, create a flow from the top navigation.
  
![Add Flow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/AddFlow.JPG)  

* For the text value create  FreshDesk from Connector  and will select a trigger "When a ticket is created" The trigger is available with FreshDesk Connector.
  
![FreshDesk](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/TicketTrigger.JPG)  

* Add Next action Predict Wich is available under Common Data Service. Action has some parameter to fill like 
  * Model - Select SentimentAnalysis Model
  * Text Language - enter "en" i.e English. You can mention the language in which support request is made
  * Text Value- The text sends in support ticket or description of Ticket
  
  ![predict](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/PredictSentiment.JPG)  

* You will add an create record action of common data service here which will store output of predict action into an Entity. Bind the return out of “Predict” action along with the output of previous trigger that have ticket details.

![Record](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/CreateRecordSentiment.JPG)

  And It is done, save the flow and you will be auto-intimated when a new support request is received on the portal, the flow will trigger and store the output in the entity. You can store the output to any data source as you wish and get the report from there.
You have stored the result in my Entity as below:

![Entities](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/EntitiesSentiment.JPG)

Below is the report using above data in Power BI that is more useful in analysis.

![Result](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/ResultSentiment.JPG)

## Download Template
* (https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/PowerAutomateFlows/SentimentAnalysis.zip)

## Reference links
* https://radacad.com/sentiment-analysis-application-microsoft-power-automate-power-apps-and-ai-builder-part-1
* https://www.ignatiuz.com/blog/power-platform/sentiment-analysis-with-power-automate-and-ai-builder/

