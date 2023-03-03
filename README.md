# WiTWhiteHat

UBS Asset Management has a Legacy  Architecture uses lot of Batch process using Autosys as its Scheduler - this has resulted in thousands of Autosys jobs. With Cloud Migration we had to lift and shift these Autosys Jobs into Azure VMs, as this is the only solution available.

Solution: We have created Azure Functions where files are processed when the event is triggered and notificaiton is sent via email. Can be leveraged further to End of Day Settlement Calculation, Event Based File Processing and Monitoring/Alerting.

### Advantages/Business Benifits

- Way without providing or managing infrastructure
- Capability to run based on event
- Only Pay when you process
- Save Development and manaintanance time

![alt text](https://github.com/ShwetaBarge/WiTWhiteHat/blob/feature/azure-function-serverless-app/AzureFunction%20Integration.jpg)

