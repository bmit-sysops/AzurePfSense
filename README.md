# AzurePfSense

## Introduction

These ARM templates deploy a pfSense NVA in Azure using linked templates. It creates the following environment:

* Virtual Network with 3 subnets
    * Gateway subnet (for future use)
    * Front-end subnet (WAN side)
    * Back-end subnet (LAN side)
* Managed disk from vhd
* pfSense virtual machine

## Parameters

All parameters are passed to the 'main' ARM template azuredeploy.json. They are forwarded to the linked templates. Here an overview per linked template:

>*Convention: [data type]name in the linked template(name in the main template): description*

## Deployment

To deploy the ARM teplate using PowerShell:

```PowerShell
New-AzureRmDeployment -Location <location> -TemplateFile <path to azuredeploy.json> -TemplateParameterFile <path to azuredeploy.parameters.json>
```