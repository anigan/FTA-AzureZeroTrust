# Zero Trust Security for Applications in Azure

Main Article - <https://docs.microsoft.com/en-us/security/zero-trust/applications>

To get the full benefit of cloud apps and services, organizations must find the right balance of providing access while maintaining control to protect critical data accessed via applications and APIs.

The **Zero Trust** model helps organizations ensure that apps, and the data they contain, are protected by:

-   Applying controls and technologies to discover Shadow IT.
-   Ensuring appropriate in-app permissions. 
-   Limiting access based on real-time analytics. 
-   Monitoring for abnormal behavior. 
-   Controlling user actions. 
-   Validating secure configuration options. 


## Things an FTA engineer can advise the customer to do

I.  Adopt [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security), which works with services to optimize visibility, governance actions, and usage. Requires Azure Ad Premium P1.

1.  [Review what apps can beconnected](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps) with the Cloud App Security API integration, and connect the appsyou need. Use the deeper visibility gained to investigate activities, files, and accounts for the apps in your cloud environment.


1.  Set up [Cloud Discovery](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery), which analyzes your traffic logs against Microsoft Cloud App Security's catalog of over 16,000 cloud apps. The apps are ranked and scored, based on more than 90 risk factors.

2.  [Discover and identify shadow IT](https://docs.microsoft.com/cloud-app-security/tutorial-shadow-it#phase-1-discover-and-identify-shadow-it) to find out what apps are being used, following one of three options:

    1.  Deploy the [Cloud App Security log collector](https://docs.microsoft.com/cloud-app-security/discovery-docker) on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.

    1.  Integrate Cloud App Security with your proxy.

3.  Identify the [risk level](https://docs.microsoft.com/cloud-app-security/risk-score) of specific apps:

    1.  In the Cloud App Security portal, under Discover, click **Discovered apps**. Filter the list of apps discovered in your organization by the risk factors you are concerned about.

    1.  Drill down into the app to understand more about its compliance by clicking the app name and then clicking the **Info** tab to see details about the app's security risk factors.

4.  [Evaluate compliance and analyze usage](https://docs.microsoft.com/cloud-app-security/tutorial-shadow-it#phase-2-evaluate-and-analyze):

    1.  In the Cloud App Security portal, under Discover, click **Discovered apps**. Filter the list of apps discovered in your organization by the compliance risk factors you are concerned about. For example, use the suggested query to filter out noncompliant apps.

    1.  Drill down into the app to understand more about its compliance by clicking the app name and then clicking the **Info** tab to see details about the app's compliance risk factors.

    1.  In the Cloud App Security portal, under Discover, click **Discovered apps** and then drill down by clicking on the specific app you want to investigate. The Use tab lets you know how many active users are using the app and how much traffic it's generating. If you want to see who, specifically, is using the app, you can drill down further by clicking **Total active users**.

    1.  [Dive deeper](https://docs.microsoft.com/cloud-app-security/discovered-apps#deep-dive-into-discovered-apps) into discovered apps. View subdomains and resources to learn about specific activities, data access, and [resource usage](https://docs.microsoft.com/cloud-app-security/discovered-apps#discover-resources-and-custom-apps) in your cloud services.