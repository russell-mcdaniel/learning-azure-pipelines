# Learning Azure Pipelines

A learning project for Azure Pipelines.

## Phase I

The first iteration deploys a default ASP.NET Core Web Application using a DevOps Project created directly from the Azure portal. It is unclear at this point how this differs from creating Azure DevOps Services project from the DevOps Services web site and creating a pipeline from there.

* Creating a DevOps Project in Azure creates the following:
  * DevOps Project resource in Azure (in its own resource group)
  * Project in Azure DevOps Services (doesn't connect to existing project)
  * Pipeline in Azure DevOps Services project
  * The build creates the following Azure resources:
    * Resource Group
    * App Service
    * App Service plan
    * Application Insights

Based on this behavior, it seems like the better course is to manually create pipelines in an Azure DevOps Services project that is also manually created in order to control the details of each element. The linkage to the Azure Portal does not seem to be a high-value element of the integration.

* The pipeline agent had to be updated to the "windows-2019" agent specification from "vs2017-win2016" in order to build the .NET Core 3.0 project.

* Deleting the resource group for the DevOps Project in Azure does not delete the project that gets created in Azure DevOps Services.

## Phase II

Create a pipeline by hand from an Azure DevOps Services project.
