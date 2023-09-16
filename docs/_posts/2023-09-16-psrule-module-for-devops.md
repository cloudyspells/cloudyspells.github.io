---
layout: post
title: "PSRule module for Azure DevOps available for feedback"
date: September 16, 2023
author: "Roderick Bant"
tags:
  - azure devops
  - pipelines
  - ci/cd
  - azure
categories:
  - Azure DevOps
excerpt_separator: <!--more-->
---
I have been a long time user of Azure DevOps and I have been using the Microsoft
PSRule module for checking my Bicep templates for quite a while now. I like the
flexible rule engine allowing to check for a wide range of issues. Now I have
developed a PSRule module for checking Azure DevOps projects for common
configuration issues. The module is available on
[GitHub](https://github.com/cloudyspells/PSRule.Rules.AzureDevOps) and can be 
installed from the PowerShell Gallery.

Please note it is in early stage of development so I am very much looking
forward to your feedback and contributions.

<!--more-->

## Using the module

To use this module, you need to have _PSRule_ installed.
You can install it from the PowerShell Gallery:

```powershell
Install-Module -Name PSRule -Scope CurrentUser
```

Once you have PSRule installed, you can install this module
from the PowerShell Gallery:

```powershell
Install-Module -Name PSRule.Rules.AzureDevOps -Scope CurrentUser
```

Once you have both modules installed, you can run an export of
your Azure DevOps project and run the rules against it. The `-PAT`
value needs to be an Azure DevOps Personal Access Token with
sufficient permissions to read the project data.

```powershell
$export = Export-AzDevOpsRuleData `
    -Organization "MyOrg" `
    -Project "MyProject" `
    -PAT $MyPAT `
    -OutputPath "C:\Temp\MyProject"
Assert-PSRule `
    -InputPath "C:\Temp\MyProject" `
    -Module PSRule.Rules.AzureDevOps
```
