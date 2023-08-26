# ghost-sytac-assignment

# azure.ghost-web-app-for-containers

A one-click [Ghost](https://ghost.org/) deployment on [Azure Web App for Containers](https://azure.microsoft.com/en-us/services/app-service/containers/).

## Deploy

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FBabug01%2Fghost-sytac-assignment%2Fmain%2Fghost.json)

## Getting Started

This is an Azure Web app deployed as a container . It uses [the custom Ghost Docker image with Azure Application Insights support](https://github.com/Babug01/ghost-sytac-assignment/tree/main/ghostapp) and [Azure Database for MySQL Flexible Server](https://learn.microsoft.com/en-us/azure/mysql/flexible-server/overview) to store the application data.

The Azure Web app configuration is provided as a ready-to-use ARM template that deploys and configures all requires Azure resources:

- a Web app and App Hosting plan for running the container;
- a Key Vault for storing secrets such as database passwords;
- a Log Analytics workspace and Application Insights component for monitoring the application;
- an Azure Database for MySQL server;
- an [Azure Front Door](https://docs.microsoft.com/en-us/azure/frontdoor/) endpoint with a [WAF policy](https://docs.microsoft.com/en-us/azure/web-application-firewall/afds/afds-overview) _or_ an [Azure CDN](https://docs.microsoft.com/en-us/azure/cdn/) profile and endpoint for offloading the traffic from the Web app depending on the specified input parameter (deploymentConfiguration).

All resources have their diagnostic settings configured to stream resource logs and metrics to the Log Analytics workspace.
