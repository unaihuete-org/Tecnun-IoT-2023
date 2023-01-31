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

## Control your device

1. To send a command from IoT Central to your device, select the **Commands** view for your device. The smartphone app can respond to three commands:

    ![image](https://user-images.githubusercontent.com/64772417/215789183-f50f1780-a5a1-4665-b552-068130d2148c.png)

1. To make the light on your smartphone flash, use the **LightOn** command. Set the **duration** to three seconds, the **pulse interval** to five seconds, and the number of **pulses** to two. Select Run to send the command to the smartphone app. The light on your smartphone app flashes twice.

1. To see the acknowledgment from the smartphone app, select command history.

Fell free to try the other commands.

## Create rules 

Get started with IoT Central rules. IoT Central rules let you automate actions that occur in response to specific conditions. The example in this quickstart uses accelerometer telemetry from the phone to trigger a rule when the phone is turned over.

The smartphone app sends telemetry that includes values from the accelerometer sensor. The sensor works slightly differently on Android and iOS devices:

- **Android**: when the phone is lying on its back, the z value is greater than **9**, when the phone is lying on its front, the z value is less than **-9**.
- **iOS**: when the phone is lying on its back, the z value is less than **-0.9**, when the phone is lying on its front, the z value is greater than **0.9**.

1. To add a new telemetry-based rule to your application, in the left pane, select **Rules**.

1. To create a new rule, select **Create a rule**.

1. Enter **Phone turned over** as the rule name.

1. In the **Target devices** section, select **IoT Plug and Play mobile** as the **Device template**. This option filters the devices the rule applies to by device template type. You can add more filter criteria by selecting **+ Filter**.

1. In the **Conditions** section, you define what triggers your rule. Use the following information to define a single condition based on accelerometer z-axis telemetry. This rule uses aggregation, so you receive a maximum of one email for each device every five minutes:

    **Android**
    | Field            | Value            |
    |------------------|------------------|
    | Time aggregation | On, 5 minutes    |
    | Telemetry        | Acceleration / Z |
    | Operator         | Is less than     |
    | Aggregation      | Minimum          |
    | Value            | -9               |

    **iOS**
    | Field            | Value            |
    |------------------|------------------|
    | Time aggregation | On, 5 minutes    |
    | Telemetry        | Acceleration / Z |
    | Operator         | Is greater than  |
    | Aggregation      | Maximum          |
    | Value            | 0.9              |

    ![image](https://user-images.githubusercontent.com/64772417/215791578-ba708e05-4505-4b40-8013-9d2bd1dcc1cb.png)


1. To add an email action to run when the rule triggers, in the **Actions** section, select **+ Email**.

1. Use the information in the following table to define your action and then select **Done**:

    | Setting      | Value                    |
    |--------------|--------------------------|
    | Display name | Your phone moved         |
    | To           | Your email address       |
    | Notes        | Your phone is face down! |

    > NOTE: To receive an email notification, the email address must be a user ID in the application, and the user must have signed in to the application at least once. Ask help to the teacher if an another account should be added to IoT central.
    
1. Select **Save**. Your rule is now listed on the **Rules** page.

Shortly after you save the rule, it becomes live. When the conditions defined in the rule are met, IoT Central sends an email to the address you specified in the action.

To trigger the rule, make sure the smartphone app is sending data and then place it face down on your desk. After five minutes, IoT Central sends you an email to notify you that your smartphone is face down.

After your testing is complete, disable the rule to stop receiving the notification emails in your inbox.

## Create a Job

You can use Azure IoT Central to manage your connected devices at scale through jobs. Jobs let you do bulk updates to device and cloud properties and run commands.

In our case we will use it to schedule a command execution.

1. In the Azure IoT Central website, on the left pane, select **Jobs**.

1. Select + New.

1. On the **Configure your job** page, enter a name (for example, **LightsNightOn**) and description to identify the job you're creating.

    ![image](https://user-images.githubusercontent.com/64772417/215795287-30909369-2b0a-4b81-a17c-5a3df19b3a10.png)
    
1. Enter your **Iot Plug and Play** devices as your **Device Group**.

1. Choose **Command** option for *Job Type** and select command "Lighton".

    - Provide following parameters:
        - Duration: 5
        - Pulse interval: 3
        - Pulses: 3
        
1. Click on **Next**.

1. On the **Delivery Options** page, click **Next**.
1. On the **Schedule** page, **enable** schedule. Define a **one-time** recurrent job, starting 3 minutes after your local time (in order to execute it 3 minute later). 1. Click on **Next** , review the settings and **Schedule**.

Wait for the job to execute succesfully. Once executed, your smartphone light should switch on. You can review the job history execution from the **Jobs** option on the left column and open the latest execution:

![image](https://user-images.githubusercontent.com/64772417/215799102-08823bae-6b29-4564-87ed-fba740bde5cb.png)
    
## Create an IoT central Dashboard (NOT GUIDED EXERCISE)

In the IoT Central app, go to **Dashboards** and create your own dashboard showing the information collected from your IoT device (smartphone).

    >Note: it is easier to start choosing **Start with Devices option**
    
![image](https://user-images.githubusercontent.com/64772417/215868037-d70057ee-4c08-4e97-a44b-aa9c72733a7e.png)

    >Note: the dashboard will have to shown to the teacher by the end of the lab.

## Data Explorer (NOT GUIDED EXERCISE)

Azure IoT Central provides rich analytics capabilities to analyze historical trends and correlate telemetry from your devices. To get started, select Data explorer on the left pane.

The analytics user interface has three main components:

- **Data configuration panel**: On the configuration panel, select the device group for which you want to analyze the data. Next, select the telemetry that you want to analyze and select the aggregation method for each telemetry. The Group By control helps to group the data by using device properties as dimensions.



- **Time control**: Use the time control to select the duration for which you want to analyze the data. You can drag either end of the time slider to select the time span. The time control also has an Interval size slider that controls the bucket or the interval size used to aggregate the data.

- **Chart control**: The chart control visualizes the data as a line chart. You can toggle the visibility of specific lines by interacting with the chart legend.

![image](https://user-images.githubusercontent.com/64772417/215869337-1f61e65a-8e9e-4b6a-bef7-f9002a1a37ae.png)

**TO DO!**: Create a query to analyze the 3 acceleration axis (x,y,z), save the query and add it to the Dashboard. **Example shown below**.

![image](https://user-images.githubusercontent.com/64772417/215870769-4c937518-61da-4944-8376-acbdcdd9357d.png)

## File upload from IoT device

IoT Central lets you upload media and other files from connected devices to cloud storage. You configure the file upload capability in your IoT Central application, and then implement file uploads in your device code.

Optionally, you can manage and preview files uploaded by your devices inside your IoT Central application.

In order to do so, we need to link a Azure Storage Account, resource used to keep our files.

### Create Azure Storage Account

1. Go to the [Azure Portal](https://portal.azure.com/), and click on **Create a resource**.
1. Search for **Storage Account** and click on **Create>Storage Account**. Provide the following properties.
    - Resource Group : **Create new** > Name it **TecnunIotDay1** and click **OK**.
    - Storage account name: Soomething unique, only lowercase allowed, for example **iotcentralNAMEsa**.
    - Region: closest one, for example **West Europe**
    - Performance: **Standard**
    - Redundancy: **LRS**
1. **Review** and **Create**. Open the resource once created.
1. In the created Storage Account resource, go to **Containers** and click on **+Container**:
    - Name: **Images**
    - Public access level: **Container (anonymous...**
1. **Create**: this will be the location were IOT device files will be uploaded.
1. On the Storage Account page, go to **Access Keys**, **copy and keep the key1**.
![image](https://user-images.githubusercontent.com/64772417/215892436-389a5872-f61a-43a5-bc80-bf7c0905c0da.png)


### Configure device file Uploads in IoT central

Open the Iot central website and the previously created App:

![image](https://user-images.githubusercontent.com/64772417/215863145-ddb724d9-a19b-4375-a49f-db5f30cdf76f.png)

1. Navigate to the **Application** section in your application.

1. Select **Device file storage**.

1. Select the storage account and container(images) created before.

1. To enable users to view and manage uploaded files inside IoT Central, set **Enable access to On.**

1. Select **Save**. When the status shows **Configured**, you're ready to upload files from devices.

    ![image](https://user-images.githubusercontent.com/64772417/215863557-e4c78465-2b4c-44fc-8dbd-5654a4fee627.png)

### Test upload files for Plug and Play App

1. Go to your smartphone, open the Plug and Play app, and choose the **Image upload** tab.

    ![image](https://user-images.githubusercontent.com/64772417/215865111-bdf9ea69-52b4-4ba6-9078-3f46ed49b477.png)

1. Select an image from gallery or take a picture with the camera. **Succesfully uploaded ...** will be shown when uploaded.
1. Open the IoT Central website, go to your Device and select the **Files** to see the uploaded pictures.

    ![image](https://user-images.githubusercontent.com/64772417/215865879-1b0ef6c7-dd3e-4942-844e-5a9b9e19aac5.png)

1. Confirm the pictures are located in the previosly selected Storage Account. Open the Storage Account in the [Azure Portal](https://portal.azure.com/), go to **Containers > images** . You will find a new folder with your deviceID and the pictures will be located under the folder.

    ![image](https://user-images.githubusercontent.com/64772417/215866460-9a9d27b5-16f0-47d8-9df8-3e7758f6b09a.png)

## Analyze uploaded Images with Azure Computer Vision

In this exercise, we are going to see how to integrate IoT solutions with Computer Vision AI by using an Azure Logic App.

Azure Logic Apps is a cloud-based platform for creating and running automated workflows that integrate your apps, data, services, and systems.

### Create Logic App

1. Go to the Azure Portal, click on **Create a resource**. Search for **Logic App** and click on **Create > Logic App**.
    - Resource Group: use same one used for Storage Account
    - Logic App name: anything unique, for example, **iottecnun-NAME-la**
    - Publish: **Workflow**
    - Region: closest, for example, **West Europe**
    - Plan type: **Consumption**
    - Zone Redundancy: **Disabled**

1. **Review + create** > **Create**.
1. Once deployed, **Go to resource**.
1. On the **Logic Apps Designer** page, select **Blank Logic App**.
![image](https://user-images.githubusercontent.com/64772417/215891298-88936793-509f-435f-b6ce-7bf45adfd41e.png)
1. We are going to define a trigger, whenever a new image is uploaded, the logic app will execute. Search for **Azure Blob Storage** and choose the trigger **When a blob is added or modified (properties only)(V2)**.
1. Set up the connection for this blob trigger and create it:
    - Connection name: **sa-conn**
    - Authentication type: **Access key**
    - Azure Storage Account  name or ... : **name of previously created Storage Account**
    - Azure Storage Account Access Key: **paste Storage Account access key copied/stored before**
    - **Create**

1. Once the connection is setup, you can define the parameters for the **When a blob is added...** trigger:
    - Storage account name: use connection...
    - Container: this will be the folder where images are uploaded **images/YOURDEVICEID**.
    - Number of blobs to return: **1**
    - How often do you want to check for items: **1 Minute**

1. Click on **+ New Step**. Search for **HTTP** and select it.

TODO
1. Click on **+ New Step**. Search for **Insert Entity (V2)(preview)** and select it.
1. Setup the connection to **Azure Table Storage**:
    - Connection name: **sa-table-conn**
    - Authentication Type: **Access Key**
    - Azure Storage Account  name or ... : **name of previously created Storage Account**
    - Shared Storage key: **paste Storage Account access key copied/stored before**
    - **Create**

1. Once connection is setup, you can define the parameters for **Insert Entity (v2) (Preview)**
    - Storage account name: use connection...
    - Table: select **analyzedImages** table
    - Entity: 
        '''
            {
              "Image": "",
              "PartitionKey": "",
              "RowKey": "",
              "SmartCaption": ""
            }
        '''
        **Select variables shown in picture!**
       



1. TODO --> send a picture from phone to IOT central --> trigger a Logic App for Custom Vision??
    - Upload picture to IOT Central : https://learn.microsoft.com/en-us/azure/iot-central/core/howto-configure-file-uploads
        - SA --> public container!!
    - Azure Function needed for image resize! https://community.dynamics.com/business/b/threadpunter/posts/azure-functions-resize-images-uploaded-to-blob-storage
1. Analyze with Data Explorer:https://learn.microsoft.com/en-us/azure/iot-central/core/quick-export-data
1. Add Data Export to Storage Account.


