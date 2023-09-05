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