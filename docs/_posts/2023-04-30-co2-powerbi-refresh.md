---
layout: post
title: "Perform energy intensive Power BI dataset refreshes when carbon emissions are low"
date: April 30, 2023
author: "Roderick Bant"
tags:
  - azure
  - carbon-emissions
  - power-bi
  - analytics
  - data
categories:
  - Green Cloud
excerpt_separator: <!--more-->
---
Recently I released the
[carbon-appinsights](https://github.com/cloudyspells/carbon-appinsights)
project. This project allows you to log emissions data from
[ElectricityMaps.com](https://www.electricitymaps.com/) to an Application
Insights instance. Today I released a first sample that demonstrates how you
can use the Azure Monitor data to trigger a Power BI dataset refresh when
carbon emissions are low in your region.

![Power BI dataset refresh](/assets/images/la-lowco2-refresh-pbi.png)

<!--more-->

## Running the sample

The sample is available on GitHub:
[cloudyspells/carbon-appinsights-samples](https://github.com/cloudyspells/carbon-appinsights-samples/tree/main/samples/refresh-pbi-dataset). You can
deploy the sample simply from the command line with `az-cli` and `bicep` from
the command line after setting up the parameters file with your desired
configuration which mainly consists of the region you want to monitor and the
Power BI dataset you want to refresh. After running the deployment you need to
authenticate with your Power BI account and grant the application access to
your Power BI workspace.

Of course to use the sample you need to have the carbon-appinsights project up
and running. You can find the instructions for that project in the README file
on GitHub: [cloudyspells/carbon-appinsights](https://github.com/cloudyspells/carbon-appinsights).

## How it works

The sample consists of an Azure Monitor Alert that is triggered when the carbon
intensity in your region is below a certain threshold. The alert is configured
to trigger a Logic App that in turn triggers a Power BI dataset refresh. As
refreshes of datasets trigger all kinds of processing events in Power BI, it is
is useful to only trigger the refresh when the carbon intensity is low.
