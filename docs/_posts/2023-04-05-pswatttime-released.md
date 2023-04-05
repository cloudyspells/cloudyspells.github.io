---
layout: post
title: "PSWattTime Released"
date: April 5, 2023
author: "Roderick Bant"
tags: ["carbon-emissions","powershell-module","powershell","azure"]
excerpt_separator: <!--more-->
---

The [PSWattTime](https://github.com/cloudyspells/PSWattTime)
module has been released! This module allows you to query the
[WattTime.org](https://www.watttime.org/) API to get the
carbon emissions of a given Azure region. I use the module in
infrastructure-as-code test deployments to ensure that we are not deploying to
regions with high carbon emissions when the only purpose is to
test the deployment itself.

<!--more-->

## Getting Started

To get started, you can install the module from the PowerShell Gallery:

```powershell
Install-Module PSWattTime
```

Login to Azure Powershell:

```powershell
Login-AzAccount
```
Register an account at [WattTime.org](https://www.watttime.org/) and login to
WattTime.org:

```powershell
New-WattTimeAccount -Username <YOUR_USERNAME> `
  -Password '<YOUR_PASSWORD>' `
  -Email '<you@domain.com>' `
  -Organization <YOUR_ORGANIZATION>

$token = Get-WattTimeAuthToken -Username '<YOUR_WATTTIME_USERNAME>' `
  -Password '<YOUR_WATTTIME_PASSWORD>'

```

Then you can query the API for the carbon emissions of a given Azure region:

```powershell
Get-WattTimeForAzureRegion -Region westeurope -AuthToken $token
```
