# Stormshield Network Security VM with 2 network interfaces

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fstormshield%2Fazure-templates%2Fmaster%2Fsns%2Fsns-2-nics%2Ftemplate.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a><a href="http://armviz.io/#/?load=https://raw.githubusercontent.com/stormshield/azure-templates/master/sns/sns-2-nics/template.json" target="_blank">
  <img src="http://armviz.io/visualizebutton.png"/>
</a>

This Azure Resource Manager template deploys a SNS VM with 2 network interfaces.


* The virtual network has a public subnet facing Internet and a private subnet for servers
* A route table is created to route trafic from the private network through the SNS appliance

<img src="img/topo-2nics.png" alt="network topology">

## Note about the password:

The password must not contain the following characters: ``" ' ` \ $``

If the password can not bet set, the following error is raised:
```
ARM.ResourceOperationFailure.OSProvisioningInternalError/OSProvisioningError
ProvisioningResultMessage:[ProvisionError] Failed to provision: [OSUtilError] Failed to set password for admin
```

## Next configuration steps:

* Setup Filtering and NAT masquerading for the Private subnet on the SNS appliance
* Deploy servers in the private subnet
* Configure NAT redirection to publish services


### Additional information

About VM with multiple network interfaces:

[https://azure.microsoft.com/en-us/documentation/articles/virtual-networks-multiple-nics/](https://azure.microsoft.com/en-us/documentation/articles/virtual-networks-multiple-nics/)