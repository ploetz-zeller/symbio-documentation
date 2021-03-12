# Side to Side and Point to Side

## The goal of P2S

The goal of Point to side is to connect a single computer system to a secured, VNet via a VPN tunnel.  
The system can be a single external computer or an Azure resource such as a WebApp.

## The goal of P2P

The goal of side to side is to connect a local network to a VNet in Azure.  
In this way, cloud resources can be accessed securely via the internal network without being accessible via the Internet.  
Conversely, it is possible for Azure systems to reach a local resource without being reachable over the Internet.

## The the described target

In order to better understand the configurations, here is the scenario and what is to be achieved.

* In Azure, an App Servcie was created, e.g. a SolMan interface, which must access local resources.  
* The service is deployed in a subnet within a VNet connected to a gateway.  
* To test the connections, an Azure VM is placed in another subnet of the same VPN.  
* A connection to the local network is configured on the gateway.

![NetworkMap](media\NetworkMap.jpg "NetworkMap")
