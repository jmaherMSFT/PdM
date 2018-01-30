# Deploying IoT PdM solution using ARM templates

Azure IoT Suite provides an easy way to deploy and get started with an IoT scenario solution deployed on Microsoft Azure platform. However, if you want to have a finer grained control over your deployment, the current deployment solution does not give you those knobs and dials. Our intent is to both give you a way to deploy the underlying platform resources, as well as describe the innerworkings of the solution.

In order to expedite this example we started with deploying a solution using the [Azure IoT Suite portal](http://www.azureiotsuite.com) ([www.azureiotsuite.com](www.azureiotsuite.com)).

![AzureIoTSuite.com](../Assets/img/AzureIoTSuiteCom.png)

Not all of the Azure subscriptions are the same, and sometimes, you may encounter a failure during deployment because of a missing resource provider. We encountered a missing provider (microsoft.machinelearning).

One of the means for determining the cause of a failing deployment is to go to Azure portal at [portal.azure.com](http://portal.azure/), select the resource group (same as your solution name), and look at the "Activity Log" as seen below:
![ActivityLog](../Assets/img/ResourceGroupActivityLog.png)

After seeing the first deployment failing, we noticed that the "microsoft.machinelearning" resource provider was not registered on our subscription, and we simply had to go to Azure Cloud Shell

![CloudShell](../Assets/img/CloudShell.png)

and register the missing resource provider.

```PowerShell
Register-AzureRmResourceProvider -ProviderNamespace "microsoft.machinelearning"
```

 After the solution is successfully deployed, you can then go to "Automation Script" for the resource group, and export. However, there are some resources you cannot export yet.

 Our goal is not to get you through all of the steps before, and deploy a solution using the AzureIoTSuite.com interface but give you a starting point for deploying the Azure IoT PdM solution using ARM templates.

You can deploy the templates using multiple ways.
 
* **Azure Portal:** We can take advantage of the deployment functionality on the portal, by appending the URL encoded URL of the template, with:

 ```HTML
 <a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FMSIndustryExperiences%2FPdM%2FErcenk%2FDeploy%2Ftemplate.json" target="_blank">
  <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
 ``` 
  in an A tag, with a reference to the deploy button as below (please see the raw version of this markdown file.)

  <a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FMSIndustryExperiences%2FPdM%2FErcenk%2FDeploy%2Ftemplate.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
  </a>

* **PowerShell:** Pelase see [https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-template-deploy](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-template-deploy) for details.

* **Azure CLI:** Pelase see [https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-template-deploy-cli](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-template-deploy-cli) for details.

* **Visualisation:** There is also a visualisation tool to show the resources and their dependencies.

  ```HTML
    <a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FMSIndustryExperiences%2FPdM%2FErcenk%2FDeploy%2Ftemplate.json" target="_blank">
      <img src="http://armviz.io/visualizebutton.png"/>
    </a>
  ```

  <a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FMSIndustryExperiences%2FPdM%2FErcenk%2FDeploy%2Ftemplate.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
  </a>