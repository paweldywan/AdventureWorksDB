# AdventureWorksDB

A SQL Server database project that implements inventory tracking functionality for the AdventureWorks business scenario. This project is built using the Microsoft.Build.Sql SDK-style format for modern SQL Server development.

## Overview

The AdventureWorksDB project contains database objects for managing inventory operations, including:

- **Tables**: Database schema for storing inventory-related data
- **Stored Procedures**: Business logic for inventory change tracking and operations

### Project Contents

- **Tables**
  - `InventoryLog` - Tracks inventory changes and modifications

- **Stored Procedures**
  - `uspLogInventoryChange` - Logs inventory changes with audit trail capabilities

## Prerequisites

- .NET SDK (for building the project)
- SQL Server 2016 or later (for deployment)
- SqlPackage CLI tool (for publishing/deployment)

## Build

To build the project and generate a deployable DACPAC file:

```bash
dotnet build
```

This creates a DACPAC (Data-tier Application Package) in the `bin/Debug/` directory that can be deployed to any SQL Server instance.

## Deployment

### Using SqlPackage CLI

To deploy to a local SQL Server instance:

```bash
sqlpackage /Action:Publish /SourceFile:bin/Debug/AdventureWorksDB.dacpac /TargetServerName:localhost /TargetDatabaseName:AdventureWorksDB
```

### Install SqlPackage CLI

If you don't have SqlPackage installed, you can install it as a dotnet global tool:

```bash
dotnet tool install -g microsoft.sqlpackage
```

For more deployment options and authentication methods, see the [SqlPackage Reference](https://aka.ms/sqlpackage-ref).

### Deploying with VS Code

You can also use the SQL Database Projects extension for VS Code to publish and manage your database project directly within the editor.

## Development

This project follows the SDK-style SQL project format, which provides:

- Version control friendly schema definition
- Integrated build and deployment pipeline
- Support for modern SQL development workflows
- Easy integration with CI/CD pipelines
