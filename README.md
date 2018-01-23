# PdM
## Improvements on the Microsoft IoT Predictive Maintenance Packaged Solution
Microsoft has published a number of packaged solutions demonstrating the use of various Azure services in the context of IoT scenarios. One of those solutions is for the predictive maintenance scenario.

We will be introducing some components and implementations on the existing PdM solution in this repository to demonstrate the Microsoft Azure platform's capabilities.

We will start with introducing the ARM templates to deploy the PdM solution.

The solutions are deployed using a [portal](https://www.azureiotsuite.com/), with the intention of making it easier to deploy them.

# MISSING PIECES
We are not adding the MSDeploy extension to the web apps, since we see that as a separate step when deploying the code to the App Service.