# Identity for Zero Trust Security in Azure

## Objectives

1. Cloud identity federates with on-premises identity systems.

2. Conditional Access policies gate access and provide remediation activities.

3. Analytics improve visibility.

4. Identities and access privileges are managed with identity governance.

5. User, device, location, and behavior is analyzed in real time to determine risk and deliver ongoing protection.

6. Integrate threat signals from other security solutions to improve detection, protection, and response.

## Things to do in FTA

1. [Connect on prem Active Directory to Azure AD](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/identity/azure-ad).
2. Choose an Authentication Option and make decisions to sync or not sync password hashes.

3. Only bring the identities you absolutely need and use this opportunity to leave stale and traditional service accounts behind.

4. [Enable Azure AD Identity Protection - Requires Premium P2](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/overview-identity-protection)

5. Put Azure AD in the path of every access request.

6. [Integrate Apps with Azure AD](https://docs.microsoft.com/en-us/security/zero-trust/identity#integrate-all-your-applications-with-azure-ad).

7. Roll out Azure Ad MFA and disable legacy authentication.

8. Enable Azure AD Conditional Access. Refer to [deployment guidance](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/plan-conditional-access) and [best practices](https://aka.ms/resilientaad).

9. [Register devices with Azure AD](https://docs.microsoft.com/en-us/security/zero-trust/identity#register-devices-with-azure-ad-to-restrict-access-from-vulnerable-and-compromised-devices) and register mobile devices with intune.

10. Integrate Azure AD monitoring and reporting with [Azure Sentinel](https://docs.microsoft.com/en-us/azure/sentinel/connect-azure-active-directory) or any [other SIEM/non-SIEM solution](https://docs.microsoft.com/en-us/azure/active-directory/reports-monitoring/plan-monitoring-and-reporting).

11. [Secure priveleged access and enable Azure Priveleged Identity Management](https://docs.microsoft.com/en-us/azure/active-directory/roles/security-planning).

12. Govern access with [Entitlement Management access packages](https://docs.microsoft.com/en-us/azure/active-directory/governance/entitlement-management-access-package-create) or [Self Service group management](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/groups-self-service-management) and [Self Service Application access](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/manage-self-service-access).

13. [Enable Passwordless Authentication](https://docs.microsoft.com/en-us/azure/active-directory/authentication/howto-authentication-passwordless-deployment) with FIDO 2.0 devices and mobile apps.

14. [Enable Microsoft Cloud App Security integration with Identity Protection](https://docs.microsoft.com/en-us/security/zero-trust/identity#enable-microsoft-cloud-app-security-integration-with-identity-protection).

15. [Enable Conditional access integration with Microsoft Cloud App Security](https://docs.microsoft.com/en-us/security/zero-trust/identity#enable-conditional-access-integration-with-microsoft-cloud-app-security).

16. Enable [Microsoft Defender for Identity](https://docs.microsoft.com/en-us/defender-for-identity/what-is).
