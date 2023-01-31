# Tecnun IoT DAY 1

## Introduction

During this first day you will design an IoT solution in Azure, using your smartphone as an Iot device with IoT Plug and Play smartphone app.

Azure IoT Central is a fully managed software-as-a-service (SaaS) platform for IoT device management and real-time data analytics. It provides an easy-to-use interface for setting up and managing IoT devices, and enables users to remotely monitor and control their devices, visualize and analyze real-time data, and create custom dashboards.

IoT Plug and Play is a new capability in Azure IoT Central that makes it easier for users to connect and manage IoT devices. It provides a pre-built device model for common IoT devices and reduces the amount of code required to integrate with IoT Central. This makes it faster and easier for users to start getting value from their IoT devices. It offers an smartphone app to simulate an IoT device experience. 

![image](https://user-images.githubusercontent.com/64772417/215782493-6a560431-4d81-460c-865c-968cdb97d733.png)

## Create an IoT Central application

Navigate to the [Azure IoT Central Build](https://aka.ms/iotcentral) site. Then sign in with the account associated with your Azure subscription.

IoT Central provides various industry-focused application templates to help you get started. This quickstart uses the Custom application template to create an application from scratch:

1. Navigate to the **Build** page and select Create app in the Custom app tile:

    ![image](https://user-images.githubusercontent.com/64772417/215783216-e8d2e7c1-fe45-4a9a-8abc-caa73dcf018e.png)

    If you're prompted to sign in, use the Microsoft account associated with your Azure subscription.

1. On the New application page, make sure that Custom application is selected under the Application template.

1. Azure IoT Central automatically suggests an Application name based on the application template you've selected. Enter your own application name such as **Tecnun-IoT-NAME-Day1** quickstart app.

1. Azure IoT Central also generates a unique URL prefix for you, based on the application name. You use this URL to access your application. Change this URL prefix to something more memorable if you'd like. This URL must be unique.

    ![image](https://user-images.githubusercontent.com/64772417/215783772-040984d3-6263-495d-97f7-d7e7d548a140.png)

1. For this quickstart, leave the pricing plan set to **Standard 0**.

1. Select your subscription in the Azure subscription drop-down.

1. Select your closest location in the Location drop-down (for example, "West Europe")

1. Review the Terms and Conditions, and select Create at the bottom of the page. After a few seconds, your IoT Central application is ready to use:

    ![image](https://user-images.githubusercontent.com/64772417/215784062-089649e6-7b7f-41be-81d3-834bc10bb309.png)
    





















1. Connect App to Iot Central and review data/commands available: https://learn.microsoft.com/en-us/azure/iot-central/core/quick-deploy-iot-central
    - Overview gives default dashboard --> create one later
1. Create rules https://learn.microsoft.com/en-us/azure/iot-central/core/quick-configure-rules?tabs=android
    - I get -9 accelerometer face up phone
    
1. Create a Job --> Schedule sending of a command
1. TODO --> send a picture from phone to IOT central --> trigger a Logic App for Custom Vision??
    - Upload picture to IOT Central : https://learn.microsoft.com/en-us/azure/iot-central/core/howto-configure-file-uploads
        - SA --> public container!!
    - Azure Function needed for image resize! https://community.dynamics.com/business/b/threadpunter/posts/azure-functions-resize-images-uploaded-to-blob-storage
1. Analyze with Data Explorer:https://learn.microsoft.com/en-us/azure/iot-central/core/quick-export-data
1. Add Data Export to Storage Account.


