# Teams eva

This connector has been created using  [COMPLETAR]

This application is a Spring Boot app and uses the [Azure web service] to deploy to Azure.

# 1. Deployment

- [Documentation](https://docs.google.com/document/d/1M8wZc1t_-Yi0ZYzZW3eozkiFZ31uxEdv/edit?usp=drive_web&ouid=100246362218061619640&rtpof=true)

# 2. Prerequisites

- Java 1.8+
- Install [Maven](https://maven.apache.org/)
- eva's preinstallation
- An account on [Azure](https://azure.microsoft.com) if you want to deploy to Azure.
- A Team's account

# 3. Azure account configuration

- From the root of this project folder: 
  - Create a folder with the name deploymentTemplates
  - Create a json named template-with-preexisting-rg.json with the following scheme: [template-with-preexisting-rg.json] (https:\\...)
  
- Following the steps of this [document](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-deploy-az-cli) open a terminal and type: 

  - Login in your account: **az login** 
  - Establish a connection: **az account set --subscription "*azure-subscription*"**
  - Deployment in the resource group: **az deployment group create --resource-group "*resource-group-name*" --template-file ".\deploymentTemplates\template-with-preexisting-rg.json" --parameters appId="*appId*" appSecret="*appSecret*" botId="*botId*" newWebAppName="*appService*" existingAppServicePlan="*appServicePlan*" appServicePlanLocation="*appServicePlanLocation*" --name "*botName*"**

Setting the fields by the desired names 

# 4. Deployment the code in the azure account
The steps to follow when deploying the code in the account previously created are described below. A number of modifications need to be made first.
## 4.1 Before the deployment

Modify the pom.xml file:

 - Set resource-group name 
 - Set appName name
 
With the values chosen.

Modify the .properties 

 - Set MicrosoftAppId 
 - Set MicrosoftPassword
	
## 4.2 Deployment the code in Azure

It will be necessary to use maven:

From the root of this project folder execute the folowing comands: 

 - mvn clean package
 - mvn azure-webapp:deploy
	
*Note:

In the document referenced ##1 you will find the explanation of how to deploy the code without using Maven.

# 5. Create Microsoft Teams Aplication

 - It is necessary to create a manifest by changing the data for the example that you will find in the following link [Manifiest-Example] (https:\\)
 - Make a .zip with the manifest and the images for the icons to the app.
 
 - Upload the manifest on Teams. 
 
 


