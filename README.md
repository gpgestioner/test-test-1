# Dpella.io
This repo contains the source code and documentation powering [Dpella.io](https://www.dpella.io/ "Dpella.io")

 **Introduction**  ![](https://img.shields.io/badge/Dpella.io-Demo-success)
 
At DPella, we believe that privacy solutions are increasingly becoming an essential segment of any industry. However, privacy is hard to get right! We’ve only just started, but we already know that every privacy-related-products require to be built around solid mathematical foundations to provide strong guarantees; an aspect that we embrace and we are experts at.

Our solutions are designed to enable your company to perform data analytics on private datasets while respecting the privacy of individuals.

##### Web Interface 
This system has an intuitive interface which allows a simple and attractive navigability, we hope you have a good experience when browsing our site.

## Documentation

#### This system runs in visual studio 2019 Community, It is composed of the following technologies:

 ![VSIDE](https://img.shields.io/badge/Visual%20Studio%202019-IDE%20Community-inactive)
 ![MVC](https://img.shields.io/badge/MVC-architecture%20pattern-success)
 ![REST](https://img.shields.io/badge/Service%20REST-Web%20Api-success)
 ![C](https://img.shields.io/badge/C%23-Backend-green)
 ![HTML5](https://img.shields.io/badge/HTML5-HiperText%20Markup%20language-informational)
 ![CSS](https://img.shields.io/badge/CSS-styles-9cf)
 ![Razor](https://img.shields.io/badge/Razor-Markup%20syntax-blue)
 ![.NETFramework](https://img.shields.io/badge/.Net%20Framework%204.6.1-Developer%20Pack-informational)
 ![EntityFramework](https://img.shields.io/badge/Entity%20Framework-6.x-blue) 
 ![Newtonsoft](https://img.shields.io/badge/Newtonsoft%20JSON-12.0.3-blue)
 ![MvcContrib](https://img.shields.io/badge/MvcContrib-2.0.95-blue)
 ![Charts](https://img.shields.io/badge/plotly.com%2Fjavascript-Charts-blue)

Our system is a web service with a web interface, developed in C# language using the .NET Framework platform, which is Microsoft's IDE (Integrated Development Environment).

> **Remember:** that the system consumes a web service, but stores it in a database, we need to have SQL Server and management installed to manage the database from there, **if there is no connection with the database the system will not work**.

### 1. Install Visual studio 

To install visual studio 2019 you need to enter here  [Visual Studio 2019 Community](https://visualstudio.microsoft.com/es/thank-you-downloading-visual-studio/?sku=Community&rel=16 "Visual Studio 2019 Community")

Before cloning it, we must have visual studio 2019 Community installed with the following worklands:

<img src="https://i.imgur.com/OSVH976.png" title="ASP.NET y Web" />

select and install them -> <img src="https://i.imgur.com/BO7MRVn.png" title="install it" />

 - inside visual studio check **Tools** -> **options** -> **Restore packages**, check that the boxes are activated
 
   <img src="https://i.imgur.com/Fx9kIwV.png" title="source: tools -> options" />

### 2. install SQL Server and Sql Management
- Link to download SQL Server(Express) [SQL Server - Express](https://www.microsoft.com/es-es/sql-server/sql-server-downloads "SQL Server - Express")
- Link to download Sql Management Studio (SSMS) [Management Studio - SSMS](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15 "SSMS")
<img src="https://i.imgur.com/wyhD42q.png" title="sql server and management" />

 Help tutorial to install SQL Server and Management-> [SQL Server and Management (Youtube)](https://www.youtube.com/watch?v=RvMthhog1H4 "help tutorial to install SQL Server and Management")
 - Once the management is installed, in your local environment add the script that we are going to provide you, inside the ScriptDB folder.
 - The script is located in the folder Documentation / scriptVersions / DpellaQA-v1.0.sql
  - We open Sql Management
  - we position ourselves in the folder that contains the script
  - we drag the script to the management, and drop it in the workspace
   
   <img src="https://i.imgur.com/m8KmEBF.png" title="drag script example" />
   
  - we can visualize the script, as we will see in this example:
   
   <img src="https://i.imgur.com/Z5PnB8D.png" title="script example" />
   
  - we stop at this part, and choose **"master"**, the next thing would be to execute it
   
   <img src="https://i.imgur.com/UfTFnL7.png" title="how to execute" />
   
  - after that we should see it in our databases.
   
<br>

### 3. if you already have everything installed,  clone the repository

- **clone the repository** from console, visual studio or sourcetree tool
<img src="https://i.imgur.com/DkUcNGN.png" title="how to clone" />

- open the project, click on **solution "project"** -> **compile project**

<img src="https://i.imgur.com/M1w7oUS.png" title="how to compile project" />

- After that, we have several ways to reestablish the connection with the database, but for now we will show you the following:
  - Inside the project we will find a Web.config file, we open it and we position ourselves in <connectionStrings> inside we will see an add tag, that is our string to configure 
  - we will have to change the data of the connectionString
   - Data Source = "name server"
   - initial catalog = "database name"
   - if you have username and password add them, otherwise it is not necessary
  <img src="https://i.imgur.com/wowP1cf.png" title="Change connection string" />

- as a last step, accept in the changes "yes to all". If all is well, we are ready

**Running Locally**  **=>** **Step 4**
-- Run IIS Explorer (your Browser) on your local machine
-- Open http://localhost:XXXX (project port) to open the site in your favorite browser

<br>

## Configuration

- This project was started in a .Net Framework MVC 4.6.1 structure, as you have read earlier in this document, implementing that model, we also have within our architecture, we can find the services, which for now we present the logs technique and our connection to the REST api.
- The base configuration of the project is the one created by the developers based on the updates provided by the Dpella api.
- Our Web service is running on a SQL Server

##### REST service
- Remember that this project is connected to the web service to work, for that we need a class that does this serialization. So once you see that the web service is working correctly, our site will have full functionality
- Make the calls to the dpella endpoints, which work with data privacity, receiving the Dataset, Structure and Histogram lists, methods which return a *responseDTO*.

- the process to generate an Analyze in the view is as follows:
  - Enter **Datasets**
  - *Choose a column*
  - Choose the type of **Histogram** *and press continue*
  - You will see that you can perform your *analysis* by calculating the ***epsilon*** and the ***beta*** with the amount of **bins**.

##### Charts of plotly 
![Charts](https://img.shields.io/badge/plotly.com%2Fjavascript-Charts-9cf) [Plotly / Charts Javascript](https://plotly.com/javascript/error-bars/#horizontal-error-bars "Plotly / Charts Javascript")
- We use plotly as a graphics library, which is an open source library that provides what we need to make our graph. Histogram and Error Bar, etc.
