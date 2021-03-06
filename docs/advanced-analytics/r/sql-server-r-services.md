---
title: R Services in SQL Server 2016 | Microsoft Docs
description: Overview introduction to SQL Server Services, R support for in-database analytics
ms.prod: sql
ms.technology: machine-learning

ms.date: 08/27/2018  
ms.topic: overview
author: HeidiSteen
ms.author: heidist
manager: cgronlun
---
# R Services in SQL Server 2016
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

SQL Server 2016 R Services is an add-on to a database engine instance, used for executing R code on SQL Server. 
Code runs in an extensibility framework, isolated from core engine processes, but fully available to relational data as stored procedures, as T-SQL script containing R statements, or as R code containing T-SQL. 

R Services includes a base distribution of R, overlaid with enterprise R packages from Microsoft so that you can load and process large amounts of data on multiple cores and aggregate the results into a single consolidated output. Microsoft's R functions and algorithms are engineered for both scale and utility: delivering predictive analytics, statistical modeling, data visualizations, and leading-edge machine learning algorithms in a commercial server product engineered and supported by Microsoft. 

R libraries include RevoScaleR, MicrosoftML, and others. Because R Services is integrated with the database engine, you can keep analytics close to the data and eliminate the costs and security risks associated with data movement.

## Components

SQL Server 2016 is R only. The following table describes the features in SQL Server 2016.

| Component | Description |
|-----------|-------------|
| SQL Server Launchpad service | A service that manages communications between the external R runtimes and the SQL Server instance. |
| R packages | [**RevoScaleR**](revoscaler-overview.md) is the primary library for scaleable R. Functions in this library are among the most widely used. Data transformations and manipulation, statistical summarization, visualization, and many forms of modeling and analyses are found in these libraries. Additionally, functions in these libraries automatically distribute workloads across available cores for parallel processing, with the ability to work on chunks of data that are coordinated and managed by the calculation engine.  <br/>[**MicrosoftML (R)**](https://docs.microsoft.com/machine-learning-server/r-reference/microsoftml/microsoftml-package) adds machine learning algorithms to create custom models for text analysis, image analysis, and sentiment analysis. <br/>[**sqlRUtils**](generating-an-r-stored-procedure-for-r-code-using-the-sqlrutils-package.md) provides helper functions for putting R scripts into a T-SQL stored procedure, registering a stored procedure with a database, and running the stored procedure from an R development environment.<br/>[**olapR**](how-to-create-mdx-queries-using-olapr.md) is for specifying MDX queries in R.|
| Microsoft R Open (MRO) | [**MRO**](https://mran.microsoft.com/open) is Microsoft's open-source distribution of R. The package and interpreter are included. Always use the version of MRO installed by Setup. |
| R tools | R console windows and command prompts are standard tools in an R distribution.  |
| R Samples and scripts |  Open-source R and RevoScaleR packages include built-in data sets so that you can create and run script using pre-installed data |
| Pre-trained models in R | Pre-trained models are created for specific use cases and maintained by the data science engineering team at Microsoft. You can use the pre-trained models as-is to score positive-negative sentiment in text, or detect features in images, using new data inputs that you provide. The models run in R Services, but cannot be installed through SQL Server Setup. For more information, see [Install pre-trained machine learning models on SQL Server](../install/sql-pretrained-models-install.md). |

## How to get started

Start with setup, attach the binaries to your favorite development tool, and write your first script.

**Step 1:** Install and configure the software. 

+ [Install SQL Server 2016 R Services (In-Database)](../install/sql-r-services-windows-install.md)

**Step 2:** Gain hands-on experience using either one of these tutorials:

+ [Tutorial: Learn in-database analytics using R](../tutorials/sqldev-in-database-r-for-sql-developers.md)
+ [Tutorial: End-to-end walkthrough with R](../tutorials/walkthrough-data-science-end-to-end-walkthrough.md)

**Step 3:** Add your favorite R packages and use them together with packages provided by Microsoft

+ [R Package management for SQL Server](install-additional-r-packages-on-sql-server.md)


## See also

 [Install SQL Server 2016 R Services](../install/sql-r-services-windows-install.md)
