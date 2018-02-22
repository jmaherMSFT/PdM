# Variations on the Microsoft IoT Predictive Maintenance Packaged Solution

Microsoft publishes several packaged IoT demonstrations using Azure services. One of those solutions is for the predictive maintenance scenario.

In this repository, we are introducing components and implementations for the existing PdM solution to demonstrate the Microsoft Azure platform's capabilities.

The solutions can be easily deployed using a [portal](https://www.azureiotsuite.com/). We are adding more details and variations on the existing implementations to provide finer grained controls.

## Architecture

The Azure IoT Suite documentation provides a high-level view of the architecture [here](https://docs.microsoft.com/en-us/azure/iot-suite/iot-suite-predictive-walkthrough).

When you deploy the solution, either through the [www.azureiotsuite.com](https://www.azureiotsuite.com/) or the provided templates, you end with the following components deployed.

![architecture](./Assets/img/Architecture.png)

## Source Code

Source code for the PdM solution is found [here](https://github.com/Azure/azure-iot-predictive-maintenance)

## Section 1: Deployment with ARM Templates

We start by introducing the ARM templates to deploy the PdM solution. The templates are in the [Deploy](./Deploy/README.md) folder.

## Missing Pieces

We aren't adding the MSDeploy extension to the web apps, we see that as a separate step when deploying the code to the App Service.
