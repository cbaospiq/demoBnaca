# Teams eva

This connector allows a bot created in eva to use Teams as a channel. 

This application is a Spring Boot app and uses the [Azure web service](https://azure.microsoft.com)  to deploy to Azure.

You can find a [document](https://drive.google.com/file/d/1M8wZc1t_-Yi0ZYzZW3eozkiFZ31uxEdv/view?usp=sharing) where you can find more information on how to deploy the connector and create the application in Teams.

# 1. Prerequisites

- Java 1.8+
- Install [Maven](https://maven.apache.org/)
- eva's preinstallation
- An account on [Azure](https://azure.microsoft.com) if you want to deploy to Azure.
- A Team's account

# 2. General characteristics

In order to create a bot in Teams, it is necessary to create a *web* channel in eVA. In this way, the responses can be represented in Teams via this connector. 

The types of responses that this connector processes are: 
 - Text
 - Image
 - Carousel

As well as **buttons** and **quickReply**. 

In addition, this part has the option of having **custom responses**. You only need to include the json of the type of response you want to represent in the cockpit response. 

# 3. EVA connection

After the creation a bot in EVA with a web channel, we have to modify the values concerning the bot in the aplication.properties file:

 - **channel.id.map** and set msteams value.
 - **eva.server.broker** url broker
 - **broker.bot.name** bot name 
 - **broker.bot.locale** language bot 

# 3. Azure account configuration

For the deployment in Azure of the Teams and eva connector and the subsequent creation of the bot it is necessary to have: 

 - Resource group
 - App Service plan
 - App Service
 - Bot Channels Registration

# 4. Deployment the code in the azure account

The steps to follow when deploying the code in the account previously created are described below. A number of modifications need to be made first.
## 4.1 Before the deployment

Modify the pom.xml file:

 - Set resource-group name 
 - Set appName name
 
with the necessary azure account values

Modify the .properties 

 - Set MicrosoftAppId 
 - Set MicrosoftPassword
	
## 4.2 Deployment the code in Azure

It will be necessary to use maven:

From the root of this project folder execute the folowing comands: 

 - **mvn clean package**
 - **mvn azure-webapp:deploy**
	
*Note:

In the document referenced ##1 you will find the explanation of how to deploy the code without using Maven.

# 5. Create Microsoft Teams Aplication

 - It is necessary to create a manifest by changing the necessary data [here](https://drive.google.com/file/d/11wneNSdHSNcAQ7NB7MDPoeQpa3i7UL40/view?usp=sharing)
 
 - Make a .zip with the manifest and the images for the icons to the app. Example [manifiest.zip](https://drive.google.com/file/d/1FOwlkhCawFNjA7r8DMzf-zhYSuvPuTQR/view?usp=sharing)
 
 - Upload the manifest on Teams. 

*Note:

For more information about how must being values at the [manifiest](https://docs.microsoft.com/es-es/microsoftteams/platform/resources/schema/manifest-schema)
 
 


