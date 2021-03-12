# Point to Side

*For the scenario described, it is assumed that a virtual network gateway already exists and that it is connected to a Vlan that has two subnets.  
One subnet for a web service and another with an existing test VM.*

## The Local gateway

Create a **Local Network Gateway**.
As the endpoint, specify either your Static-IP address or a *Fully Qualified Domain Name* (FQDN) (e.g. a DynDns address) if your Local Gateway does not provide a Static-IP.

For the address range, enter the ranges behind your firewall that can be reached by Azure resources. e.g. 192.168.0.0/24

## The Connection

Navigate to the new **Local Network gateway** and select Connections under Settings.  
Create a new connection there.  

Enter the virtual network gateway as the destination in the connection and store a shared key (PSK).  
The PSK can be predefined by your firewall, if you don't have one, enter a value you have created yourself. This **MUST** also be configured in your firewall.
Then select the supported protocol (IKEv1/IKEv2).

After your connection has been created, navigate to it and to the **Configuration** of **Settings**

If necessary, you can manually configure your encryption methods here.  
Information about these settings can be found in your firewall and the Microsoft [documentation](https://docs.microsoft.com/en-us/azure/vpn-gateway/ipsec-ike-policy-howto).

## Connect your hardware

To establish an active connection, you need to connect your hardware to Azure resources.  
For this you need the public IP address of your virtual network gateway as well as your PSK.  
For device-specific configurations and Donwnloads, refer to the Microsoft [documentation](https://docs.microsoft.com/en-us/azure/vpn-gateway/tutorial-site-to-site-portal#configure-your-vpn-device) or your device manufacturer's documentation.

In the connection resource overview you can see that your VN tunnel and connection have been successfully established.  
Please note that the data counter must be increased at the latest after a ping test.  
Otherwise there is an error with the connection, this can be due to missing routes or rules on the local side.

![Connection-Established](media\AZ-Connection.jpg "Connection-Established")

## Test the connection

As soon as your connection was successful and all rules are entered, you can test the connections via a ping.

* Your local resources should now be able to reach the test VM. (Here the IP 10.10.1.4)  
![tcpping-local-vm](media\Local-Ping-VM-s2s.png "tcpping-local-vm")
* Your test VM should now be able to reach the local resource. (Here the IP 192.169.90.2)  
![tcpping-vm-local](media\AZ-Vm-Ping-Local-s2s.png "tcpping-vm-local")
* You should now be able to reach the local resource and the test VM via the console of the WebService.  
![tcpping-s2s](media\AZ-AppService-tcpping-s2s.png "tcpping-s2s")

## More informations

More technical information can be found in the official Microsoft [documentation](https://docs.microsoft.com/en-us/azure/vpn-gateway/tutorial-site-to-site-portal).  
Here you can also find officially supported hardware and default configurations for it.
