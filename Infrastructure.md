# Zero Trust Security for Infrastructure in Azure

## Objectives

1. Workloads are monitored and alerted to abnormal behavior.

2. Every workload is assigned an app identity—and configured and deployed consistently.

3. Human access to resources requires Just-In-Time.

4. Unauthorized deployments are blocked, and alert is triggered.

5. Granular visibility and access control are available across workloads.

6. User and resource access segmented for each workload.

## Things that an FTA engineer can advise the customer to do

Implement Tenant Baselines - <https://docs.microsoft.com/en-us/security/zero-trust/infrastructure#infrastructure-zero-trust-deployment-guide>

1. Implement [Azure Arc](https://azure.microsoft.com/services/azure-arc/) to centrally manage your environment.

2. Enable Azure Security Center and apply security baseline policy definitions enabled by it.

3. Apply ASC Endpoint Protection and Vulnerability Management controls.

4. Enable Azure ATP to monitor the identities.

5. Control sizing, regions and other settings through Azure policy.

6. Enable JIT in Azure AD for priveleged access.

7. Implement Azure Blueprints.

8. Create custom roles and assign permissions using RBAC.

9. Apply network segmentation methodologies.

10. Enable Azure Sentinel and monitor all azure services as well as VMs.

11. Advise the customer to deploy Gen 2 virtual machines and enable [trusted launch](https://docs.microsoft.com/en-us/azure/virtual-machines/trusted-launch).

12. Use Azure Key Vault's [Managed HSM](https://docs.microsoft.com/en-us/azure/key-vault/managed-hsm) or [Dedicated HSM](https://docs.microsoft.com/en-us/azure/dedicated-hsm) to generate  and store keys.


