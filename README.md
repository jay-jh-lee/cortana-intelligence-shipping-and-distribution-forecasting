# Shipping and Distribution Demand Forecasting

This folder contains the automated deployment instructions for the deployable Shipping and Distribution Demand Forecasting solution in the Cortana Intelligence Gallery. To start a new solution deployment, visit the gallery page [here](https://gallery.cortanaintelligence.com/Solution/2108aa00e76f43489c9c20fdd7659527).

## Summary

Time series data can often be disaggregated by attributes of interest to form groups of time series or a hierarchy. For example, one might be interested in forecasting demand of all products in total, by location, by product category, by customer, etc. Forecasting grouped time series data is challenging because the generated forecasts need to satisfy the aggregate requirement, that is, lower-level forecasts need to sum up to the higher-level forecasts. There are many approaches that solve this problem, differing in the way they aggregate individual time series forecasts across the groups or the hierarchy. This solution uses a middle-out approach to forecasting grouped time series ([Hyndman et al.](http://otexts.org/fpp/9/4)).

In this preconfigured solution we deploy a forecasting model that reads hierarchical or grouped data, and computes forecasts disaggregated by all input variables. In this text, we will refer to both hierarchial and grouped time series as hierarchical time series, for simplicity.

## Description

#### Estimated Provisioning Time: 15 Minutes

The Cortana Intelligence Suite provides advanced analytics tools through Microsoft Azure — data ingestion, data storage, data processing and advanced analytics components — all of the essential elements for building an demand forecasting solution for shipping and distribution.

This solution combines several Azure services to provide powerful advantages. Azure SQL Server instance is used for storing historical distribution data, Azure Machine Learning (AML) webservice for hosting the R forecasting code, Azure Storage Account for intermediate storage of generated forecasts, and Azure Data Factory orchestrates and schedule the entire workflow.

The '*Deploy*' button will launch a workflow that will deploy an instance of the solution within a Resource Group in the Azure subscription you specify. The solution includes multiple Azure services (described below) along with Azure functions that, among other tasks, simulate the data and populates the database with it, so that immediately after deployment you have a working end-to-end solution. 

## Solution architecture

The following chart describes the solution architecture. 

![Solution Architecture](https://github.com/Azure/cortana-intelligence-shipping-and-distribution-forecasting/blob/master/Technical%20Deployment%20Guide/media/architecture.PNG)

### What's under the hood

The solution uses five types of resources hosted and managed in Azure: 

* *Azure SQL Server* instance (Azure SQL) for persistent storage, 
* *Azure Machine Learning* (AML) webservice to host the R forecasting code, 
* *Azure Blob Storage* for intermediate storage of generated forecasts,
* *Azure Data Factory* (ADF) that orchestrates regular runs of the AML model,  
* *Power BI* dashboard to display and drill down on the forecasts. 

## Using the forecasting solution: Getting started

See the [Technical Solution Guide](./Technical%20Deployment%20Guide/Technical-Solution-How-to-Guide.md) for a full set of instructions on how to put together and deploy the Shipping and Distribution Demand Forecasting Solution using the Cortana Intelligence Suite. For technical problems or questions about deploying this solution, please post in the issues tab of the repository.

## Solution Dashboard

The snapshot below shows the PowerBI dashboard generated by the solution that gives insights into the forecasted demand.

![PowerBI Snapshot](https://github.com/Azure/cortana-intelligence-shipping-and-distribution-forecasting/blob/master/Technical%20Deployment%20Guide/media/powerbisnapshot.PNG)

## Business Use Case

We adapted this solution for a supply chain collaborator, Kotahi, a company that plans, sources, and delivers shipping containers for New Zealand exports. Read their [Customer Story](https://customers.microsoft.com/en-us/story/kotahi) on who they engaged Microsoft and Microsoft Dynamics 2016 Inner Circle partner UXC Eclipse to create an automated demand forecaster using our solution. The solution helped to increase accuracy and improve customer's ability to choose the right-size container ships, at the right times, and dispatch them to the right ports.





