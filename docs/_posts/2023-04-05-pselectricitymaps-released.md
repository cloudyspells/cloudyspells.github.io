---
layout: post
title: "PSElectricityMaps Released"
date: April 5, 2023
author: "Roderick Bant"
tags:
  - carbon-emissions
  - powershell-module
  - powershell
  - azure
categories:
  - Green Cloud
  - PowerShell
excerpt_separator: <!--more-->
---

The [PSElectricityMaps](https://github.com/cloudyspells/PSElectricityMaps)
module has been released! This module allows you to query the
[Electricity Maps](https://www.electricitymaps.com/) API to get the
carbon emissions of a given Azure region. At this time the endpoint and
required user account are still located at CO2signal.com, but these will be
migrated to ElectricityMaps.com in the near future by _ElectrityMaps_. I use
the module in infrastructure-as-code test deployments to ensure that we are not
deploying to regions with high carbon emissions when the only purpose is to
test the deployment itself.

<!--more-->

## Getting Started

To get started, you can install the module from the PowerShell Gallery:

```powershell
Install-Module PSElectricityMaps
```

Register an account at [CO2signal.com](https://www.co2signal.com/) and login to
Azure Powershell:

```powershell
Login-AzAccount
```

Then you can query the API for the carbon emissions of a given Azure region:

```powershell
Get-ElectricityMapsForAzureRegion -Region westeurope -AuthToken <YOUR_CO2SIGNAL_TOKEN>
```
