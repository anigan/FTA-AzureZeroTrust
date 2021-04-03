# Zero Trust Security for Networks in Azure

Main Article - <https://docs.microsoft.com/en-us/security/zero-trust/networks>

In the Zero Trust model, there are three key objectives when it comes to securing your networks:

1. Be ready to handle attacks before they happen.

2. Minimize the extent of the damage and how fast it spreads.

3. Increase the difficulty of compromising your cloud footprint.

## Things that an FTA engineer can advise the customer to do

I. Implement [Network segmentation: Many ingress/egress cloud micro-perimeters with some micro-segmentation](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/network-level-segmentation).Applications are partitioned to different Azure Virtual Networks (VNets) and connected using a hub-spoke model.

* [Create dedicated virtual networks](https://docs.microsoft.com/en-us/azure/virtual-network/quick-create-portal) for different applications and/or application components.

* Create a central VNet to set up the security posture for inter-app connectivity and connect the app [VNets in a hub-and-spoke architecture](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/hub-spoke).

* [Deploy Azure Firewall](https://docs.microsoft.com/en-us/azure/firewall/deploy-ps) in the hub VNet to inspect and govern traffic between the VNets.

II. Threat protection: Cloud native filtering and protection for known threats

Cloud applications that have opened up endpoints to external environments, such as the internet or your on-premises footprint, are at risk of attacks coming in from those environments. It is therefore imperative that you scan the traffic for malicious payloads or logic.

These types of threats fall into two broad categories:

* __Known attacks__. Threats that have been discovered by your software provider or the larger community. In such cases, the attack signature is available and you need to ensure that each request is checked against those signatures. The key is to be able to quickly update your detection engine with any newly identified attacks.

* __Unknown attacks__. These are threats that don't quite match against any known signature. These types of threats include zero-day vulnerabilities and unusual patterns in request traffic. The ability to detect such attacks depends on how well your defenses know what's normal and what is not. Your defenses should be constantly learning and updating such patterns as your business (and associated traffic) evolves.

Take these steps to protect against known threats:

1.  **For endpoints with HTTP/S traffic**, protect using [Azure Web Application Firewall (WAF)](https://docs.microsoft.com/azure/web-application-firewall/overview) by:

    1.  Turning on the default ruleset or [OWASP top 10](https://owasp.org/www-project-top-ten/) protection ruleset to protect against known web-layer attacks

    1.  Turning on the bot protection ruleset to prevent malicious bots from scraping information, conducting credential stuffing, etc.

    1.  Adding custom rules to protect against threats specific to your business.

    You can use one of two options:

    - [Azure Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-overview)

        1. [Create a Web Application Firewall policy on Azure Front Door](https://docs.microsoft.com/azure/web-application-firewall/afds/waf-front-door-create-portal).

        1. [Configure bot protection for Web Application Firewall](https://docs.microsoft.com/azure/web-application-firewall/afds/waf-front-door-policy-configure-bot-protection).

        1. [Custom rules for Web Application Firewall](https://docs.microsoft.com/azure/web-application-firewall/afds/waf-front-door-custom-rules-powershell).

    - [Azure Application Gateway](https://docs.microsoft.com/azure/application-gateway/overview)

       1. [Create an application gateway with a Web Application Firewall](https://docs.microsoft.com/azure/web-application-firewall/ag/application-gateway-web-application-firewall-portal).

       1. [Configure bot protection for Web Application Firewall](https://docs.microsoft.com/azure/web-application-firewall/ag/bot-protection).

       1. [Create and use Web Application Firewall v2 custom rules.](https://docs.microsoft.com/azure/web-application-firewall/ag/create-custom-waf-rules).


2.  **For all endpoints (HTTP or not)**, front with [Azure Firewall](https://docs.microsoft.com/azure/firewall/overview) for threat intelligence-based filtering at Layer 4:

    1.  [Deploy and configure Azure Firewall](https://docs.microsoft.com/azure/firewall/tutorial-firewall-deploy-portal) using the Azure portal.

    1.  [Enable threat intelligence-based filtering](https://docs.microsoft.com/azure/firewall/threat-intel) for your traffic.

### III. Encryption: User-to-app internal traffic is encrypted

The third initial objective to focus on is adding encryption to ensure user-to-app internal traffic is encrypted.

Follow these steps:

1.  Enforce HTTPS-only communication for your internet facing web applications by [redirecting HTTP traffic to HTTPS using Azure Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-how-to-redirect-https).

2.  Connect remote employees/partners to Microsoft Azure using the [Azure VPN Gateway](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways).

    1.  [Turn on encryption](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-security-controls#data-protection) for any point-to-site traffic in Azure VPN Gateway service.

3.  Access your Azure virtual machines securely using encrypted communication via [Azure Bastion](https://docs.microsoft.com/azure/bastion/bastion-overview).

    1.  [Connect using SSH to a Linux virtual machine](https://docs.microsoft.com/azure/bastion/bastion-connect-vm-ssh).

    1.  [Connect using RDP to a Windows virtual machine](https://docs.microsoft.com/azure/bastion/bastion-connect-vm-rdp).

### IV. Network segmentation: Fully distributed ingress/egress cloud micro-perimeters and deeper micro-segmentation

Once you've accomplished your initial three objectives, the next step is to further segment your network.


#### Partition app components to different subnets



Follow these steps:

1.  Within the VNet, [add virtual network subnets](https://docs.microsoft.com/azure/virtual-network/virtual-network-manage-subnet) so that discrete components of an application can have their own perimeters.

2.  [Apply network security group rules](https://docs.microsoft.com/azure/virtual-network/tutorial-filter-network-traffic#create-security-rules) to allow traffic only from the subnets that have an app subcomponent identified as a legitimate communications counterpart.


#### Segment and enforce the external boundaries



Follow these steps, depending on the type of boundary:

##### Internet boundary

1.  If internet connectivity is required for your application that needs to be routed via the hub VNet, [update the network security group rules](https://docs.microsoft.com/azure/virtual-network/tutorial-filter-network-traffic) in hub VNet to allow internet connectivity.

2.  [Turn on Azure DDoS Protection Standard](https://docs.microsoft.com/azure/virtual-network/manage-ddos-protection#enable-ddos-for-an-existing-virtual-network)
    to protect the hub VNet from volumetric network layer attacks.

3.  If your application uses HTTP/S protocols, [turn on Azure Web Application Firewall](https://docs.microsoft.com/azure/web-application-firewall/afds/waf-front-door-custom-rules-powershell) to protect against Layer 7 threats.


##### On-premises boundary

1.  If your app needs connectivity to your on-premise data center, [use Azure ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-portal-resource-manager) of Azure VPN [for connectivity to your hub VNet](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-howto-site-to-site-resource-manager-portal).

2.  [Configure the Azure Firewall](https://docs.microsoft.com/azure/firewall/tutorial-hybrid-ps) in the hub VNet to inspect and govern traffic.


##### PaaS services boundary

 - When using Azure-provided PaaS services (e.g., Azure Storage, [Azure Cosmos DB](https://docs.microsoft.com/azure/private-link/create-private-endpoint-cosmosdb-portal),
    or [Azure Web App](https://docs.microsoft.com/azure/private-link/create-private-endpoint-webapp-portal), use the [PrivateLink](https://docs.microsoft.com/azure/private-link/create-private-link-service-portal) connectivity option to ensure all data exchanges are over the private IP space and the traffic never leaves the Microsoft network.

### V. Threat protection: Machine learning-based threat protection and filtering with context-based signals

For further threat protection, turn on [Azure DDoS Protection Standard](https://docs.microsoft.com/azure/virtual-network/ddos-protection-overview) to constantly monitor your Azure-hosted application traffic, use ML-based frameworks to baseline and detect volumetric traffic floods, and apply automatic mitigations.

Follow these steps:

1.  [Configure and manage](https://docs.microsoft.com/azure/virtual-network/manage-ddos-protection) Azure DDoS Protection Standard.

1.  [Configure alerts](https://docs.microsoft.com/azure/virtual-network/manage-ddos-protection#configure-alerts-for-ddos-protection-metrics) for DDoS protection metrics.


### VI. Encryption: All traffic is encrypted

Finally, complete your network protection by ensuring that all traffic is encrypted.

Follow these steps:

1.  [Encrypt application backend traffic](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-ipsecikepolicy-rm-powershell) between virtual networks.

1.  Encrypt traffic between on-premises and cloud:

    1.  [Configure a site-to-site VPN](https://docs.microsoft.com/azure/expressroute/site-to-site-vpn-over-microsoft-peering) over ExpressRoute Microsoft peering.

    1.  [Configure IPsec transport mode](https://docs.microsoft.com/azure/expressroute/expressroute-howto-ipsec-transport-private-windows) for ExpressRoute private peering.

