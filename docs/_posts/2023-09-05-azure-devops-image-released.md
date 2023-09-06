---
layout: post
title: "Azure DevOps Pipeline agent image released"
date: September 5, 2023
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
Microsoft Hosted Azure DevOps agents are great for CI/CD in most projects with
the extensive built-in set of popular tools. In practice however, their
usability is limited because the Microsoft Hosted agents cannot be connected to
a private network. License limitations prevent Microsoft from distributing the
image used in their hosted pools. To speed up development and remove toil, a
pre-built version of the Microsoft Hosted image containing only the included
Open Source tools is now available in the
[Azure Marketplace](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/rtbusinessvalidation1685730553911.ado-agent-ms-stack-ubuntu2204?tab=Overview). The source code for
the project is also available on
[GitHub](https://github.com/cloudyspells/ado-agent-ms-stack) with instructions
how to get started.

<!--more-->

## What is included?

The image is based on the Microsoft Hosted Ubuntu 22.04 image and contains the
all tools included in the Microsoft Hosted image that include a license that
allows redistribution. The image is built using the same scripts as the
Microsoft Hosted image and is updated regularly. A 
[full list of included tools](https://github.com/cloudyspells/ado-agent-ms-stack/wiki/Ubuntu2204-Readme)
is available in the project wiki.

## How to use it?

The image is available in the Azure Marketplace and can be used in Azure
DevOps pipelines as a self-hosted agent. The image is available in the
all regions where Microsoft Hosted agents are available. You can also build
your own image using the scripts in the GitHub repository. Building your own
image is useful if you want to add additional tools or customize the image
further.

## What are the advantages?

When connecting to a private network is required, the Microsoft Hosted agents
cannot be used. This is a common requirement in many projects. As your
organization grows, the need for various build and deployment tools increases.
Building and maintaining your own agent images is a lot of work. Using the
pre-built image removes the need to build and maintain your own images as it
includes most popular tools. The image is also updated regularly with the
latest versions of the tools.