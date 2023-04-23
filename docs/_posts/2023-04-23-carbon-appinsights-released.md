---
layout: post
title: "Carbon AppInsights released - A new way to trigger actions based on emissions data"
date: April 23, 2023
author: "Roderick Bant"
tags:
  - azure
  - carbon-emissions
  - powershell
categories:
  - Green Cloud
excerpt_separator: <!--more-->
---
Want to trigger _Azure Logic Apps_ and _Power Automate_ flows based on carbon
emissions data? The 
[Carbon AppInsights](https://github.com/cloudyspells/carbon-appinsights)
project has been released on GitHub! This project allows you to query the Carbon
emissions data from the [ElectricityMaps.com](https://www.electricitymaps.com/)
API and add it to an _Azure Application Insights_ instance backed by a Log
Analytics workspace. You can then use the metrics sent to Application Insights
to trigger actions in _Azure Logic Apps_ and _Power Automate_ flows.

<!--more-->

This enables you to do all kinds of things with the standard functionality of
these platforms. For example, you can trigger a Logic App to start a VM or
trigger a Data Factory pipeline to start a data transfer when the carbon
emissions of a region drop below a certain threshold. You can also use the data
to trigger alerts in Azure Monitor.

## Resources

The deployment of the Carbon AppInsights project consists of the following Azure
resources:

- An _Azure Application Insights_ instance
- A _Log Analytics_ workspace
- An _Azure Function App_ with a _Timer_ trigger
- A _Storage Account_ for the Function App
- A _Key Vault_ to store the Electricity Maps API key

The Azure Function App is triggered every 20 minutes and queries the Electricity
Maps API with the
[PSElectricityMaps](https://github.com/cloudyspells/PSElectricityMaps)
module.

## Getting Started

To get started, you can deploy the Carbon AppInsights project to your Azure
subscription by forking the
[GitHub repository](https://github.com/cloudyspells/carbon-appinsights) and
following the instructions in the README.md file.
