# AzShim
Automate the deployment of Azure Monitor Diagnostic Settings for the integration with Blumira SIEM. For additional information regarding Blumira's eventhubs information please see, https://blumira.zendesk.com/hc/en-us/articles/4854089610643-Integrating-with-Microsoft-Azure-Event-Hubs#01FYS6Z0F1SG9GZFX1J6A1CGJ2.

## Pre-requisites
This script assumes the following:
1. You have an Azure subscription (have not tested with Gov Cloud only standard Azure subscriptions)
2. All of the resources you wish to monitor are contained inside of said subscription
3. All of the resources you wish to monitor are contained within the same region
4. You know or can set up an Azure CLI cloud shell or have a local machine that is using `BASH` and not `ZSH`

## Setting Up Azure Cloud Shell
Before running the script it is recommended that you set up or configure Azure Cloud Shell. You can use the defaults without issue, but when prompted for **Location** within the script, please use the region ID where you have most of your other resources in your subscription. Azure by default may place the storage account in a separate region. When starting make sure to run Azure Cloud Shell in `BASH` and not Powershell. Use this video below for help in getting started with Azure Cloud Shell (Skip to 0:58s from Cloud Guru).
[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/2pQr-w8ZiYU/0.jpg)](http://www.youtube.com/watch?v=2pQr-w8ZiYU)

## Cloning the Repo and Running the Script
To get started copy and paste the following into your Azure Cloud Shell terminal window. The following commands clone the repo, place you in the directory, set the script to have the proper permissions to run, and finally run the script.

```Bash
git clone https://github.com/Blumira/AzShim.git
cd ./AzShim
chmod +x ./AzShim.azcli
./AzShim.azcli -c
```
Once the script has started to run, it will deploy resources to all valid subscriptions that you are listed as a contributor or higher to.

## Closing Out
This script is still being worked on, in the future I hope to have a subscription selector further reducing the the need for manual input and I need to account for more resources that do not support the `Log` category in Azure Monitor Diagnostic Settings.
