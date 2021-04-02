# Zero Trust Security for Networks in Azure

Main Article - <https://docs.microsoft.com/en-us/security/zero-trust/networks>

## Objectives

In the Zero Trust model, there are three key objectives when it comes to securing your networks:

1. Be ready to handle attacks before they happen.

2. Minimize the extent of the damage and how fast it spreads.

3. Increase the difficulty of compromising your cloud footprint.


## Things that an FTA engineer can advise the customer to do

1. Implement [Network segmentation: Many ingress/egress cloud micro-perimeters with some micro-segmentation](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/network-level-segmentation).Applications are partitioned to different Azure Virtual Networks (VNets) and connected using a hub-spoke model.

* Create dedicated virtual networks for different applications and/or application components.

* Create a central VNet to set up the security posture for inter-app connectivity and connect the app VNets in a hub-and-spoke architecture.

* Deploy Azure Firewall in the hub VNet to inspect and govern traffic between the VNets.

2. Implement Azure Web Application Firewall with the default ruleset.

3. Implement Azure Front Door.

4. Implement Azure Application Gateway.

5. Deploy and configure Azure Firewall.

6. Connect remote employees/partners to Microsoft Azure using the Azure VPN Gateway.

7. Access the Azure VMs using Azure Bastion.

8. Use Azure PrivateLink.

9. Enable, Configure and manage Azure DDoS Protection Standard.

10. Configure a site-to-site VPN over ExpressRoute Microsoft peering.

11. Configure IPsec transport mode for ExpressRoute private peering.