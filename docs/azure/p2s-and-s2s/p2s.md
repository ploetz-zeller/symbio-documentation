# Point to Side

## VNet

The first thing you need is an Azure Virtual Network to be deposited their resources.  
Configure it with e.g the following values.  
|Address space|Address range|Address count
|--|--|--|  
|10.10.0.0/25|10.10.0.0 - 10.10.0.127|128|

## Subnets

In the VNet you need different subnets. In our example, we will create the following three subnets.
|Type|Name|IPv4|
|--|--|--|  
|Gateway subnet|GatewaySubnet|10.10.0.96/27|
|Subnet|VM-Subnet|10.10.0.0/29|
|Subnet|App-Services|10.10.0.64/27|

## Connect the Service

Create a new WebService, which can be configured as you need.  
Navigate to the AppService and to the point **Networking** of the **Settings** on the left side.

![Networking](media\AZ-AppService-Networking.jpg "Networking")

On the new page you can navigate to the VNet  

![Networking](media\AZ-AppService-Networking-VNet.jpg "Networking")

Click on "Add VNet" and select your required VNet on the right side.
Select "Select Existing" and choose the subnet "App-Services" from the lower dropdown.

## Connect the Test-VM

For testing purposes, you can create a virtual machine.  
When creating it select under the network tab select the previous VNet and the "VM-Subnet".  

After the VM has been created, copy the Private IP address from the overview.  
This will be 10.10.0.4 in our example.

## Create the virtual gateway

Create a resource **Virtual network gateway**.
For our example we use a gateway of type **VPN** and **Route-Based**.  
So it supports the latest encryption methods like IKEv2.  

*`If you want to configure also a Side-To-Side your hardware must support Routbased and IKEv2. Otherwise select Policy-based here`*

Find your VNet here and select the *Gateway subnet* you created before

The creation of the Gatewasy takes about 15 minutes, since a physical resource is provided on the Azure side.

## Test the connection

Navigate to the WebApp under Development Tools and open the Console.  

Execute the following command there

```cmd
tcpping 10.10.0.4:3389 
```

Your result should look something like this.
This ensures that your app can communicate within your VNetwork, across subnets.

![tcpping](media\AZ-AppService-tcpping.jpg "tcpping")

## More informations

More technical information can be found in the official Microsoft [documentation](https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-point-to-site-resource-manager-portal).  
Here you can also find how to connect to the VNet with a local computer system.  
