# WiTWhiteHat

UBS Asset Management has a Legacy  Architecture uses lot of Batch process using Autosys as its Scheduler - this has resulted in thousands of Autosys jobs. With Cloud Migration we had to lift and shift these Autosys Jobs into Azure VMs, as this is the only solution available.

<b>Solution:</b> We have created Azure Functions where files are processed when the event is triggered and notificaiton is sent via email. Can be leveraged further to End of Day Settlement Calculation, Event Based File Processing and Monitoring/Alerting.

Use Case being automated: We have application which have automated process like End of Day settlement, and Daily Nav Report Generation. (Report AUtomation). These application still depend on human intervention to be triggered or they are scheduled at a particular time. 

<b>Issues that may occur:</b>
1. When jobs are scheduled at a given time is that the Job may run even if the source input files are not available. 
2. The applications are either run on desktop/server or require some infrastructure. There is cost and effort in maintenance of both application and infrastructure.

<b>Solution:</b>
1. Developing event based solutions: Jobs will run at a defined event, therefore eleminating any error of missing source file.
2. Solution is server less, hence requiring less maintance compared to older solution in terms of cost, time, and effort.

Components:

1. Resource Group
2. Azure Storage Account
3. Blob storage
4. Azure Functions
5. SendGrid

Development 

1. Create resource group to contain all the resources you want to use. 
2. Create Azure Function App
![alt text](https://github.com/ShwetaBarge/WiTWhiteHat/blob/feature/azure-function-serverless-app/AzureFunction.jpg)
3. Select Storage Account, with the container to which you want to watch for events (events such as file upload).
![alt text](https://github.com/ShwetaBarge/WiTWhiteHat/blob/feature/azure-function-serverless-app/StorageAccount.jpg)
4. Complete Creating Function
5. Creating trigger such that whenever there is a file upload to Blob our defined task should run. Add our function code which will trigger email when there is upload to the Blob Storage.
https://github.com/ShwetaBarge/WiTWhiteHat/tree/feature/azure-function-serverless-app/techemailnotification/BlobTrigger1
6. Create SendGrid Subscription.
![alt text](https://github.com/ShwetaBarge/WiTWhiteHat/blob/feature/azure-function-serverless-app/SendGrid.jpg)
7. Integrate your SendGrid with the trigger by defining function.json: https://github.com/ShwetaBarge/WiTWhiteHat/blob/feature/azure-function-serverless-app/techemailnotification/BlobTrigger1/function.json

### Advantages/Business Benifits

- Way without providing or managing infrastructure
- Capability to run based on event
- Only Pay when you process
- Save Development and manaintanance time

![alt text](https://github.com/ShwetaBarge/WiTWhiteHat/blob/feature/azure-function-serverless-app/AzureFunction%20Integration.jpg)

