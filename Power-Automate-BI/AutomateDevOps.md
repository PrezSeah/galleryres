---
noteId: "640c8a108fc711ecb57c076a5a9176f2"
tags: []

---

# Automate DevOps Using Power Automate

Automatically create work item in Azure DevOps as creating tasks can take time away from Dev team, depleting capacity that would be better to automate.
Consider a sitiuation where you typically have the same 9 tasks across you development teams for most but not all User Stories(More on that later). Instead of tasking the team with creating the same task repeatedly for each created User Story, Product Backlog Iteam, wa can create a flow to automate this work
Follow the below step.
* Create Automate flow 
  ![NewFlow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/NewFlow.JPG)

* Choose trigger for Azure DevOps by searching for Azure DevOps and select when a work item is created and click Create.
  ![Work Item](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/WorkItemDevOps.JPG)

* In the next window, choose your organization's Account name from the available Account Name drop dwon
  https://AccountName.visualstudio.com). Next select the Project Name from the Project Name drop down (https://AccountName.visualstudio.com/ProjectName). Finally, select User Story for Type.

  ![Preview](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/AccountNameDevOps.JPG)

* To ensure that your flow only creates tasks for new User Stories that don’t already have tasks, select Condition Control.
  
  ![Condition](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/ActionDevOpsAutomate.JPG)

* Within the Condition, set Tasks Created (this is the new field you created for the User Story work item in Azure DevOps) is not equal to Created Date. There are many different conditions you can add as well to ensure you are only creating tasks for certain User Stories. But for this example, we will use just the one criterion.
  
  ![Action Detail](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/ConditionDevOps.JPG)

* Next, select Add an action under the If yes section. Search for “create a work item” and select the Azure DevOps Create a work item action.

  ![Yes Condition](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/YesConditionDevOps.JPG)

* In order to automatically create tasks and connect the action to your Azure DevOps environment using the Account and Project Name from the previously complete “When a work item is created” step, select your Account and Project Name from the list of options. Next, select Work Item Type to Task. Set the title and description of your desired task along with any additional fields you might want to set. Then, expand Advanced Options and set both the Iteration Path and the Area Path. Make sure to set the Link URL to the “When a work item is created” URL and set the Link Type to Hierarchy-reverse to create the Task as a child of the User Story.

  ![Yes Condition](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/YesDetailsDevOps.JPG)

* Repeat the Create a work item step for all the necessary Tasks, ensuring you fill in the necessary fields in the Advanced Options for your team. It is important as you are scrolling through the dynamic content pane that you select from “When a work item is created”, which is the User Story that triggered the flow to start. Additionally, you can set the Task Activity in the Other Fields section so you can categorize your Tasks appropriately (Development, Testing, Documentation, etc.) This will enable you to match up your team members’ capacity to work on certain tasks to their work.

  ![Update Work Item](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/UpdateWorkItemDevOps.JPG)

* To update the User Story that triggered this flow, set the Work Item ID to the ID from “When a work item is created” dynamic content. Then in the Other Fields options, type Tasks Created (the name of the new field you created in Azure DevOps). Next, set the value to the Created Date from “When a work item is created” dynamic content. This step will prevent the flow from running again and automatically creating duplicate tasks for the User Story.  

* We are almost done! In the If no area, select Add an action and search for “Terminate”. Next, select Terminate and set the Status to Cancelled. Finally, save your flow and test it to make sure you do not have any errors.

  ![No Condition](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/NoCondition.JPG)

## Reference Link
* https://powerobjects.com/flow/automation-using-flow-and-azure-devops/