<div align="center">
  
# OpenPLZ API

[![.Net](https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=.net&logoColor=white)](https://dotnet.microsoft.com/)
[![GitHub License](https://img.shields.io/github/license/openpotato/openplzapi?style=for-the-badge)](./LICENSE)
[![Documentation](https://img.shields.io/badge/docs-available-brightgreen?style=for-the-badge)](https://www.openplzapi.org)

</div>

The service behind the OpenPLZ API. Build with [.NET 10](https://dotnet.microsoft.com/).

## Technology stack

+ [PostgreSQL 17+](https://www.postgresql.org/) as database
+ [ASP.NET](https://dotnet.microsoft.com/apps/aspnet) as web framework
+ [Entity Framework Core](https://docs.microsoft.com/ef/) as ORM layer
+ [Swagger UI](https://swagger.io/tools/swagger-ui/) for OpenAPI based documentation

## Getting started 

The following instructions show you how to set up a development environment on your computer.

### Prerequisites

+ Set up a local PosgreSQL 17 (or higher) instance.
+ Clone or download this repository.
+ Open the solution file `OpenPlzApi.slnx` in Visual Studio 2026.

### Configure the OpenPLZ API CLI

+ Switch to the project `OpenPlzApi.CLI`.
+ Make a copy of the the `appsettings.json` file and name it `appsettings.Development.json`.
+ Exchange the content with the following JSON document and adjust the values to your needs. This configures the root folder for the data file downloads and the database connection.
  
  ``` json
  "Sources": {
    "RootFolderName": "c:\\OpenPlzApi.Downloads"
  },
  "Database": {
    "Server": "localhost",
    "Database": "OpenPlzApi",
    "Username": "postgres",
    "Password": "qwertz"
  }
  ```

### Create and populate the database

+ Build the `OpenPlzApi.CLI` project. 
+ Run the `OpenPlzApi.CLI` project with parameter `initdb --import`. This will create and populate the PostgreSQL database.

### Configure the OpenPLZ API WebService

+ Switch to the  `OpenPlzApi.WebService`. 
+ Make a copy of the the `appsettings.json` file and name it `appsettings.Development.json`.
+ Exchange the content with the following JSON document and adjust the values to your needs. This configures the database connection.

  ``` json
  "Database": {
    "Server": "localhost",
    "Database": "OpenPlzApi",
    "Username": "postgres",
    "Password": "qwertz"
  }
  ```

### Build and test the API

+ Build the `OpenPlzApi.WebService` project.
+ Run the `OpenPlzApi.WebService` project and play with the Swagger UI.

## Can I help?

Yes, that would be much appreciated. The best way to help is to post a response via the Issue Tracker and/or submit a Pull Request.
