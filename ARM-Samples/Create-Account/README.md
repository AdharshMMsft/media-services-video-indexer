
# Quickstart: Deploy Azure Video Analyzer for Media with ARM Template 

## Overview

In this Quick-Start you will create an Azure Video Analyzer for Media (formerly Video Indexer) account by using ARM template (PREVIEW)

The resource will be deployed to your subscription and will create the Azure Video Analyzer for Media resource based on parameters defined in the avam.template file.


> **Note:**
> this sample is *not* for connecting an existing Azure Video Analyzer for Media classic account to an ARM-Based Video Analyzer for Media account.

> For full documentation on Azure Video Analyzer for Media API, visit the [Developer Portal](https://aka.ms/avam-dev-portal) page.

> The current API Version is "2021-10-27-preview". Check this Repo from time to time to get updates on new API Versions.

## Prerequisites

* An Azure Media Services (AMS) account. You can create one for free through the [Create AMS Account](https://docs.microsoft.com/en-us/azure/media-services/latest/account-create-how-to).

## Deploy the sample

----

### Option 1: Click the "Deploy To Azure Button", and fill in the missing parameters


[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure-Samples%2Fmedia-services-video-indexer%2Fmaster%2FARM-Samples%2FCreate-Account%2Favam.template.json)  

----

### Option 2 : Deploy using Power Shell Script

1. Open The [Template File](avam.template.json) file and inspect its content.
2. Fill in the required parameters (see below)
3. Run the Following Power Shell commands:

* Create a new Resource group on the same location as your Azure Video Analyzer for Media account, using the [New-AzResourceGroup](https://docs.microsoft.com/en-us/powershell/module/az.resources/new-azresourcegroup) cmdlet.


```powershell
New-AzResourceGroup -Name myResourceGroup -Location eastus
```

* Deploy the template to the resoruce group using the [New-AzResourceGroupDeployment](https://docs.microsoft.com/en-us/powershell/module/az.resources/new-azresourcegroupdeployment) cmdlet.

```powershell
New-AzResourceGroupDeployment -ResourceGroupName myResourceGroup -TemplateFile ./avam.template.json
```

> **Note:**
> If you would like to work with bicep format, inspect the [bicep file](avam.template.bicep) on this repo


## Parameters

### name


* Type: string

* Description: Specifies the name of the new Azure Video Analyzer for Media account.

* required: true

### location


* Type: string

* Description: Specifies the Azure location where the Azure Video Analyzer for Media account should be created.

* Required: false


> **Note:**
> You need to deploy Your Azure Video Analyzer for Media account in the same location (region) as the associated Azure Media Services(AMS) resource exists.


### mediaServiceAccountResourceId

* Type: string

* Description: The Resource ID of the Azure Media Services(AMS) resource.

* Required: true


### managedIdentityId

* Type: string

* Description: The Resource ID of the Managed Identity used to grant access between Azure Media Services(AMS) resource and the Azure Video Analyzer for Media account.

* Required: true


### tags


* Type: object

* Description: Array of objects that represents custom user tags on the Azure Video Analyzer for Media account

 Required: false


### Notes

## Reference Documentation

If you're new to Azure Video Analyzer for Media (formerly Video Indexer), see:


* [Azure Video Analyzer for Media Documentation](https://aka.ms/vi-docs)
* [Azure Video Analyzer for Media Developer Portal](https://aka.ms/vi-docs)

* After completing this tutorial, head to other Azure Video Analyzer for media Samples, described on [README.md](../../README.md)

If you're new to template deployment, see:

* [Azure Resource Manager documentation](https://docs.microsoft.com/azure/azure-resource-manager/)
* [Deploy Resources with ARM Template](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deploy-powershell)
