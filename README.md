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
    

## Register a Device

To connect a device to your IoT Central application, you need some connection information. An easy way to get this connection information is to register your device.

To register your device:

1. In IoT Central, navigate to the Devices page and select Add a device:

    ![image](https://user-images.githubusercontent.com/64772417/215784492-6dc42c72-e3e5-4419-bf0b-8c911e95c076.png)
    
1. On the Create a new device page, accept the defaults, and then select Create.
1. In the list of devices, click on the device name (it will have your own identifier):

    ![image](https://user-images.githubusercontent.com/64772417/215785296-83c7fd3f-57fc-4b90-b31f-44900e3948d1.png)
1. On the device page, select Connect and then QR Code:

    ![image](https://user-images.githubusercontent.com/64772417/215785718-4d3d2ae3-9fc0-4021-a10e-40301c801204.png)

Keep this page open. In the next section, you scan this QR code using the smartphone app to connect it to IoT Central.

    > Note: The QR code contains the information, such as the registered device ID, your device needs to establish a connection to your IoT Central application. It saves you from the need to enter the connection information manually. ** Day 2 you will need this information**
    
## Connect your device 
    
To get you started quickly, this article uses the **IoT Plug and Play** smartphone app as an IoT device. The app sends telemetry collected from the smartphone's sensors, responds to commands invoked from IoT Central, and reports property values to IoT Central.

Install the app on your smartphone from one of the app stores:

    [![image](https://user-images.githubusercontent.com/64772417/215786495-4498fdaf-7aaf-43d8-b476-718182e2c953.png)](https://play.google.com/store/apps/details?id=com.iot_pnp)

    [![image](https://user-images.githubusercontent.com/64772417/215787188-8b12d22c-af81-4708-b3eb-cc3c66c20700.png)](https://apps.apple.com/app/iot-plug-and-play/id1563783687)

To connect the **IoT Plug and Play** app to your Iot Central application:

1. Open the IoT PnP app on your smartphone.

1. On the welcome page, select **Scan QR code**. Point the smartphone's camera at the QR code. Then wait for a few seconds while the connection is established.

1. On the telemetry page in the app, you can see the data the app is sending to IoT Central. On the logs page, you can see the device connecting and several initialization messages.

To view the telemetry from the smartphone app in IoT Central:

1. In IoT Central, navigate to the **Devices** page.

1. In the list of devices, click on the device name (random id generated for you), then select Overview:

    ![image](https://user-images.githubusercontent.com/64772417/215787592-48bd49de-2c33-4422-b3b2-5c221c8a23f2.png)

    >IMPORTANT! The smartphone app only sends data when the screen is on.


















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


