<properties
   pageTitle="Manage your applications in Visual Studio | Microsoft Azure"
   description="Use Visual Studio to create, develop, package, deploy, and debug your Service Fabric applications and services."
   services="service-fabric"
   documentationCenter=".net"
   authors="jessebenson"
   manager="timlt"
   editor=""/>

<tags
   ms.service="service-fabric"
   ms.devlang="dotnet"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na"
   ms.date="10/15/2015"
   ms.author="jesseb"/>

# Use Visual Studio to simplify writing and managing your Service Fabric applications

You can manage your Service Fabric applications and services through Visual Studio. Once you've [setup your development environment](service-fabric-setup-your-development-environment.md), you can use Visual Studio to create Service Fabric applications, add services, or package, register, and deploy applications in your local development cluster.

To manage your application, in the Solution Explorer right-click on your application project.

![Manage your Service Fabric application by right-clicking on the Application project][manageservicefabric]

## Deploying your Service Fabric application

Deploying an application combines the following steps into one simple operation.

1. Creating the application package
2. Uploading the application package to the image store
3. Registering the application type
4. Removing any running application instances
5. Creating a new application instance

In Visual Studio, you can deploy an application by choosing Deploy Solution from the Build menu. Pressing **F5** will also deploy your application and attach the debugger to all application instances.


## Adding a service to your Service Fabric application

You can add new Fabric Services to your application to extend its functionality.  To ensure the service is included in your application package, add the service through the **New Fabric Service...** menu item.

![Add a new Fabric Service to your application][newservice]

Select a Service Fabric project type to add to your application, and specify a name for the service.  See [choosing a framework for your service](service-fabric-choose-framework.md) to help decide which service type to use.

![Select a Fabric Service project type to add to your application][addserviceproject]

The new service will be added to your solution and existing application package. The service references and a default service instance will be added to the application manifest. The service will be created and started the next time you deploy the application.

![The new service will be added to your application manifest][newserviceapplicationmanifest]

## Packaging your Service Fabric application

An application package needs to be created in order to deploy the application and its services to a cluster.  The package organizes the application manifest, service manifest(s), and other necessary files in a specific layout.  Visual Studio sets up and manages the package in the application project's folder, in the 'pkg' directory.  Clicking **Package** creates or updates the application package.  You may want to do this if you deploy the application using custom Powershell scripts.

## Removing an application

You can remove an application from your local cluster using Server Explorer.  This will revert the deployment steps described above:

1. Remove any running application instances
2. Unregister the application type
3. Remove the application package from the image store

![Remove an application](./media/service-fabric-manage-application-in-visual-studio/removeapplication.png)

<!--Every topic should have next steps and links to the next logical set of content to keep the customer engaged-->
## Next steps

- [Service Fabric application model](service-fabric-application-model.md)
- [Service Fabric application deployment](service-fabric-deploy-remove-applications.md)
- [Debugging your Service Fabric application](service-fabric-debugging-your-application.md)
- [Visualizing your cluster using Service Fabric Explorer](service-fabric-visualizing-your-cluster.md)

<!--Image references-->
[addserviceproject]:./media/service-fabric-manage-application-in-visual-studio/addserviceproject.png
[manageservicefabric]: ./media/service-fabric-manage-application-in-visual-studio/manageservicefabric.png
[newservice]:./media/service-fabric-manage-application-in-visual-studio/newservice.png
[newserviceapplicationmanifest]:./media/service-fabric-manage-application-in-visual-studio/newserviceapplicationmanifest.png
