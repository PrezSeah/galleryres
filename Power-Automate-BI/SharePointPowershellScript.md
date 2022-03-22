# Execute SharePoint Online PowerShell scripts using Power Automate

Most of us would have used PowerShell for SharePoint to manage SharePoint settings at the organization level and site collection level. SharePoint Online PowerShell commands are very efficient for batch operations for e.g creating multiple sites, list items etc. To use the SharePoint Online PowerShell commands
* You must have the SharePoint Admin role or Global Administrator role in Office 365
* Install the SharePoint Online Management Shell module

As you know you must be administrator to install a PowerShell module on your workstation which not everyone will have in corporate environments.

I often use a PowerShell script to enable App Catalog at a site collection level to test the PnP webparts & extensions before deploying at the tenant level app catalog based on requirement. If you are not an SPO admin then the dependency is with the SPO admin. In this blogpost I am going to show you how to automate this process by executing PowerShell script to enable App catlog in Azure using Power Automate.

To complete this automation process, create the following two components

* Automation account in Azure with a Run Book to execute PowerShell script for enabling App Catalog in SP site
* Power automate flow to call the Run Book


## Step1: 
Go the Azure portal & create a resource Automation

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint1.JPG)

Enter the name of the automation account, select the Subscription & resource group & click Create

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint2.JPG)

## Step 2: 
After the resource is created, go to the resource & click Modules Gallery under the section Shared Resources as shown below to add the PS SPO module

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint3.JPG)

Search with the keyword “SharePoint” & click “Microsoft.Onlie.SharePoint.PowerShell” and then click Import. This step will the add the SharePoint online PowerShell module for us to use the available PS SPO cmdlets in Runbook.

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint4.JPG)
## Step3
The next step is to add the user credentials (Username & Password) of the SPO admin which is safe & secure by not hardcoding the password on the Runbook. You can also use certificates or AppID AppSecret in PnP online Powershell for creating connection to SPO.

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint5.JPG)

## Step4
Now we are good to create the Runbook, to create it click Runbooks under the section Process Automation and then click Create a runbook. Enter the Name of the Runbook, select the Runbook type to PowerShell and click Create.

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint6.JPG)

Now let’s add the code by editing the runbook to enable app catalog. The section Dynamic Parameters on the code will be passed from flow. To connect to SharePoint Online we are using the SPO admin credentials created in the previous step. Find the code below

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint7.JPG)

The runbook is now created, you can test the script by clicking on Test Pane & pass parameters (Site URL etc) to test it. Click Publish button as shown below to publish so that it can be called from Power Automate. It’s now time to create the flow

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint8.JPG)

## Power automate flow to call the Run Book
You can now create a flow with automated trigger from a SharePoint list to get the site url & Boolean value either to enable or disable the app catalog on the site. Here I will be using an Instant flow with trigger “Manually trigger a Flow”

Once the flow is created, add the action “Create Job” under the connector “Azure Automation” which is a premium connector.

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint9.JPG)

Select the Azure Subscription which has the Automation account resource with runbook>Select Resource Group>Select Automation Account>Select the Runbook name which has PS script to enable app catalog. If there is a need to wait until the automation job completes then select Yes on the field “Wait for Job”. For the dynamic parameter, write a JSON to pass the mandatory & optional parameters to the runbook script. On this example I will be passing the Site URL & Boolean value to either enable or disable app catalog using JSON as below

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint10.JPG)

If using a SharePoint list, construct the above JSON dynamically with the URL

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint11.JPG)

For the runbook parameters, you might also get an interface as shown below to pass the values (Site Url & enableAppcatalogbooleanvalue).

![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/SharePoint12.JPG)


