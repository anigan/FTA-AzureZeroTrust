__Main Article__ - https://www.microsoft.com/en-ww/security/business/zero-trust
# Introduction to Zero Trust

Attackers are evolving by the day and the types of attacks are growing sophisticated. Zero trust security assumes that everything is compromised unless proven otherwise.

In a Zero Trust model, every access request is strongly authenticated, authorized within policy constraints
and inspected for anomalies before granting access. Everything from the user’s identity to the application’s
hosting environment is used to prevent breach. We apply micro-segmentation and least privileged access
principles to minimize lateral movement. Finally, rich intelligence and analytics helps us identify what
happened, what was compromised, and how to prevent it from happening again.

## Guiding principles of Zero Trust

1. __Verify explicitly__. Always authenticate and authorize based on all available data points,
including user identity, location, device health, service or workload, data classification,
and anomalies.
2. __Use least privileged access__. Limit user access with Just-In-Time and Just-Enough
Access (JIT/JEA), risk-based adaptive polices, and data protection to protect both data
and productivity.
3. __Assume breach__. Minimize blast radius for breaches and prevent lateral movement by
segmenting access by network, user, devices, and application awareness. Verify all sessions
are encrypted end to end. Use analytics to get visibility, drive threat detection, and
improve defenses.

## Foundational elements of Zero Trust

1. Identities – whether they represent people, services, or IOT devices – define the Zero Trust control plane. When an identity attempts to access a resource, we need to verify that identity with strong authentication, ensure access is compliant and typical for that identity, and follows least privilege access principles.

2. Devices - Once an identity has been granted access to a resource, data can flow to a variety of different devices—from IoT devices to smartphones, BYOD to partner managed devices, and on-premises workloads to cloud hosted servers. This diversity creates a massive attack surface area, requiring we monitor and enforce device health and compliance for secure access.

3. Applications - Applications and APIs provide the interface by which data is consumed. They may be legacy on-premises, lift-and-shifted to cloud workloads, or modern SaaS applications. Controls and technologies should be applied to discover Shadow IT, ensure appropriate in-app permissions, gate access based on real-time analytics, monitor for abnormal behavior, control of user actions, and validate secure configuration options.

4. Data - Ultimately, security teams are focused on protecting data. Where possible, data should remain safe even if it leaves the devices, apps, infrastructure, and networks the organization controls. Data should be classified, labeled, and encrypted, and access restricted based on those attributes.

5. Infrastructure
Infrastructure (whether on-premises servers, cloud-based VMs, containers, or micro-services) represents a critical threat vector. Assess for version, configuration, and JIT access to harden defense, use telemetry to detect attacks and anomalies, and automatically block and flag risky behavior and take protective actions.

6. Networks
All data is ultimately accessed over network infrastructure. Networking controls can provide critical “in pipe” controls to enhance visibility and help prevent attackers from moving laterally across the network. Networks should be segmented (including deeper in-network micro segmentation) and real-time threat protection, end-to-end encryption, monitoring, and analytics should be employed.

