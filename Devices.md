# Zero Trust Security for Devices/Endpoints in Azure

Main Article - <https://docs.microsoft.com/en-us/security/zero-trust/endpoints>

## Objectives

There are a few key rules for securing devices and endpoints in a Zero Trust model:

Zero Trust security policies are centrally enforced through the cloud and cover endpoint security, device configuration, app protection, device compliance, and risk posture.

The platform as well as the apps that run on the devices are securely provisioned, properly configured, and kept up to date.

There is automated and prompt response to contain access to corporate data within the apps in case of a security compromise.

The access control system ensures that all policy controls are in effect before the data is accessed.

## Things that an FTA engineer can advise the customer to do

1. [Join corporate devices to Azure AD.](https://docs.microsoft.com/en-us/security/zero-trust/endpoints#register-corporate-devices-with-azure-active-directory-ad).

2. Enable Azure Sentinel and have [devices report data into it](https://docs.microsoft.com/en-us/azure/sentinel/connect-windows-security-events).


