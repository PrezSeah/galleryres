
# Convert PDF to TXT in Power Automate


In this example, we will convert a PDF file to Text (txt) in Microsoft Power Automate. You can follow the same steps if you are using Azure Logic Apps.

Our first step in setting up our flow is getting the contents of a PDF file from Azure Blob (this could be retrieved many other possible file sources as well, such as OneDrive, SharePoint, Box, Google Drive, etc.). Then, we will pass the contents of this file into the Cloudmersive PDF connector with the “Convert PDF Document to Text” action. If you are new to using one of our API Keys in Power Automate or Azure Logic Apps, you will be prompted to insert your API Key. Once this has been completed, we will pass in the desired file name. Finally, we will create a new file in your preferred file drive and store the output from the Cloudmersive connector into this output file.

![Flow](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/Image1pdftoTxt.JPG)


Then, we can run it. Below, you will see the result:

![Flow1](https://raw.githubusercontent.com/PrezSeah/galleryres/main/Power-Automate-BI/images/Image2pdftoTxt.JPG)


## Reference links
* https://cloudmersive.com/examples/convert-pdf-to-txt-in-power-automate