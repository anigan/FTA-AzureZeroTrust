# Data for Zero Trust Security in Azure

__Main Article__ - https://docs.microsoft.com/en-us/security/zero-trust/data

The three core elements of a data protection strategy are:

1. __Know your data__. If you don't know what sensitive data you have on-premises and in cloud services, you can't adequately protect it. You need to discover data across your entire organization and classify all data by sensitivity level.

2. __Protect your data and prevent data loss__. Sensitive data needs to be protected by data protection policies that label and encrypt data or block over-sharing. This ensures only authorized users are able to access the data, even when data travels outside of your corporate environment.

3. __Monitor and remediate__. You should continuously monitor sensitive data to detect policy violations and risky user behavior. This allows you to take appropriate action, such as revoking access, blocking users, and refining your protection policies.

When data and sensitive content is understood, labeled, and classified, organizations can:

* Inform and enforce policy decisions to block or remove emails, attachments, or documents.

* Encrypt files with sensitivity labels on device endpoints.

* Auto-classify content with sensitivity labels through policy and machine learning.

* Track and monitor sensitive content using policies as the content travels inside and outside your digital estate.

## Things an FTA engineer can do to meet these objectives

1. Enable [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection) to automatically classify the data.

2. Enable AIPs automatic data classification.

3. Enable AD RMS to encrypt the data based on the classification.

# Securing Databases

