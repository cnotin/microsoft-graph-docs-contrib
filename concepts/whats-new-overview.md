---
title: "What's new in Microsoft Graph"
description: "View highlights of what's new in Microsoft Graph in the past two months, what was added in earlier releases, and how you can share your ideas."
author: "angelgolfer-ms"
ms.localizationpriority: high
---

# What's new in Microsoft Graph

See highlights of what's new in the recent two months in Microsoft Graph, [what's added earlier](whats-new-earlier.md), and how you can [share your ideas](#want-to-stay-in-the-loop). For a detailed list of API-level updates, see the [API changelog](https://developer.microsoft.com/graph/changelog/). 

In addition, find out about new documentation and learning resources for released features and APIs.

> [!IMPORTANT]
> Features, including APIs and tools, in _preview_ status may change without notice, and some may never be promoted to generally available (GA) status. Do not use preview features in production apps.


## October 2023: New and generally available

### Teamwork and communications | Calls and online meetings
[Get](/graph/api/calltranscript-get) a specific [transcript](/graph/api/resources/calltranscript) or all the transcripts of an [online meeting](/graph/api/resources/onlinemeeting). _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=09e85d0c-2551-40e7-a037-1f36fade0b0b)_.

## October 2023: New in preview only

### Device and app management | Cloud PC
- [Running health checks for on premises network connection](/graph/api/cloudpconpremisesconnection-runhealthcheck?view=graph-rest-beta&preserve-view=true) can now identify the active domain join check failed because the server is not operational. This could be due to network connectivity issues, DNS resolution issues, or problems with the domain controller itself. Make sure that the domain controller is running, and that ports that are required to be open between the client computer and the domain controller are enabled and not blocked. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=80297d8c-5457-4fa1-be2b-769490b818bb)_.
- Support app scenarios to [create](/graph/api/virtualendpoint-post-onpremisesconnections?view=graph-rest-beta&preserve-view=true), [update](/graph/api/cloudpconpremisesconnection-update?view=graph-rest-beta&preserve-view=true), [delete](/graph/api/cloudpconpremisesconnection-delete?view=graph-rest-beta&preserve-view=true), or [run health checks](/graph/api/cloudpconpremisesconnection-runhealthcheck?view=graph-rest-beta&preserve-view=true) on a [Cloud PC on-premises connection](/graph/api/resources/cloudpconpremisesconnection?view=graph-rest-beta&preserve-view=true) without a signed-in user. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=cd506d8f-eddb-4d12-859d-a7894452989e)_.

### Identity and access | Directory management
Create and manage a [certificate-based application configuration](/graph/api/resources/certificateBasedApplicationConfiguration?view=graph-rest-beta&preserve-view=true) which represents a chain of trust that specifies allowed root and intermediate certificate authorities. This configuration is part of an [app management policy](/graph/api/resources/appmanagementpolicy?view=graph-rest-beta&preserve-view=true) used for [application authentication](/graph/api/resources/applicationauthenticationmethodpolicy?view=graph-rest-beta&preserve-view=true) and can restrict app developers to use only those certificates issued by authorities defined in the configuration. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=c022f245-26dd-4fd7-81f2-4297d5a37c6d)_.

### Identity and access | Identity and sign-in
Get or specify in a Microsoft Entra native [X-509 certificate-based authentication configuration](/graph/api/resources/x509CertificateAuthenticationMethodConfiguration?view=graph-rest-beta&preserve-view=true), whether Certificate Authority issuer hints are sent back to the client side to filter the certificates shown in certificate picker. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=26b75f44-c3c8-4300-a98b-2ee6c75e6146)_.

### Sites and lists
[List items](/graph/api/recyclebin-list-items?view=graph-rest-beta&preserve-view=true) in the [recycle bin](/graph/api/resources/recycleBin?view=graph-rest-beta&preserve-view=true) of a SharePoint [site](/graph/api/resources/site?view=graph-rest-beta&preserve-view=true). _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=3fdf4a8e-0ba7-405a-91d1-f7b4b6ac6983)_.

## September 2023: New and generally available

### Education
- Support app scenarios to [update](/graph/api/educationassignment-update) or [delete](/graph/api/educationassignment-delete) a [class assignment](/graph/api/resources/educationassignment) with grades for all users, or [delete](/graph/api/educationassignmentresource-delete) an [assignment resource](/graph/api/resources/educationassignmentresource) without a signed-in user. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=6c7e1673-5f35-4df3-a099-7b29652546b1)_.
- Support app scenarios to [create](/graph/api/educationassignment-post-resource) or [set up a folder](/graph/api/educationassignment-setupresourcesfolder) for [assignment resources](/graph/api/resources/educationassignmentresource) without a signed-in user. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=6c7e1673-5f35-4df3-a099-7b29652546b1)_.

### Identity and access | Partner customer administration
A Microsoft indirect reseller partner administrator can approve or reject a [reseller delegated admin relationship](/graph/api/resources/resellerDelegatedAdminRelationship) between a partner and a customer, created for them by a Microsoft indirect provider partner. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=d68a33be-ca1b-461a-b215-69ba3144a394)_.

### Search | Index
As an option, include a label to indicate a [property](/graph/api/resources/externalconnectors-property) in the [schema](/graph/api/resources/externalconnectors-schema) for an [external connection](/graph/api/resources/externalconnectors-externalconnection) is an icon URL. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=429c062a-4b3f-4ea1-ab45-d399ff6818cc)_.

### Security | Threat intelligence
- Discover referential [host pairs](/graph/api/resources/security-hostpair) observed about a [host](/graph/api/resources/security-host). Host pairs include details such as information about HTTP redirections, consumption of CSS or images from a host, and more.
- Read [SSL certificate](/graph/api/resources/security-sslcertificate) data, and [SSL certificate data observered on a host](/graph/api/resources/security-hostsslcertificate). This data includes information about the SSL certificate and the relationship between the host and the SSL certificate.
- Read [subdomain](/graph/api/resources/security-subdomain) details for a host. For every subdomain, there can be a new set of IP addresses to which the domain resolves. This can be a great data source for finding related infrastructure.
- Read [WHOIS details](/graph/api/resources/security-whoisrecord) for a host. A common function of WHOIS in threat infrastructure is to identify or connect disparate entities based on unique data shared within the records.
- _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=541c1216-7521-4a72-ac7e-7c9ab9c46e69) for the preceding updates for threat intelligence_.

### Teamwork and communications | Apps
[Get](/graph/api/teamsappsettings-get) or [update](/graph/api/teamsappsettings-update) tenant-wide [settings](/graph/api/resources/teamsappsettings) to allow or disallow installing Teams apps that require resource-specific permissions in a chat or meeting. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=e0bcac9c-8d0e-4b23-8bbf-e50150848d35)_.

### Teamwork and communications | Calls and online meetings
[Set a status message](/graph/api/presence-setstatusmessage) about a user's [presence](/graph/api/resources/presence), such as their availability or user activity. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=bb202bf3-3029-4b9a-b1be-8df926dbb45e)_.

## September 2023: New in preview only

### Device and app management | Cloud PC
- [Get the overall connection quality reports](/graph/api/cloudpcreports-getconnectionqualityreports?view=graph-rest-beta&preserve-view=true) for all devices within a current tenant during a given time period, including metrics like the average round trip time, and real-time metrics such as last connection round trip time. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=be5ebbef-56ec-465d-afbe-aef899ab7e40)_.
- [Get a usage report on Frontline Cloud PC licenses](/graph/api/cloudpcreports-getFrontlineReport?view=graph-rest-beta&preserve-view=true), for data such as service plan ID, license count, and claimed license count, for real-time, 7-day, or 28-day trend. This is a Windows 365 Frontline-branded report which replaced the report to [get shared licenses of a service plan](/graph/api/cloudpcreports-getshareduselicenseusagereport?view=graph-rest-beta&preserve-view=true). _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=4d35dcf2-2f6c-413d-a4c4-c7770152a77b)_.

### Device and app management | Corporate management
Intune September updates for the beta version. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=bad338c7-9745-4ad7-a22f-f153a2dac4fc)_.

### Education
Support app scenarios to read or write an [education module](/graph/api/resources/educationModule?view=graph-rest-beta&preserve-view=true) or [learning resource](/graph/api/resources/educationModuleResource?view=graph-rest-beta&preserve-view=true) without a signed-in user. Scenarios can include [publishing](/graph/api/educationmodule-publish?view=graph-rest-beta&preserve-view=true), [pinning](/graph/api/educationmodule-pin?view=graph-rest-beta&preserve-view=true), or [unpinning](/graph/api/educationmodule-unpin?view=graph-rest-beta&preserve-view=true) a module, or [setting up a SharePoint folder](/graph/api/educationmodule-setupresourcesfolder?view=graph-rest-beta&preserve-view=true) for resources in a module. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=3e9f0779-4339-4ce3-afea-420ed8d03f50)_.

### Identity and access | Directory management
- [Update](/graph/api/organization-update?view=graph-rest-beta&preserve-view=true) for an [organization](/graph/api/resources/organization?view=graph-rest-beta&preserve-view=true) whether it is synchronized with an on-premises directory. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=6e41743f-c9a0-4ee7-bcb8-a09ab773585b)_.
- Improve the security posture of the applications in your tenant by [configuring and limiting the certificate authority issuers](/graph/api/resources/certificatebasedapplicationconfiguration?view=graph-rest-beta&preserve-view=true) whose certificates can be assigned to your apps and service principals.

### Identity and access | Governance
- Get the date and time when an [access package subject](/graph/api/resources/accessPackageSubject?view=graph-rest-beta&preserve-view=true), which can be a user, service principal, or other entity, is to be blocked from access. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=cfb9bd20-e02b-4b0f-8f2a-7bf1aeec12e3)_.
- Check out the new documentation about [managing security alerts for Microsoft Entra roles](/graph/how-to-pim-alerts) using Privileged Identity Management APIs in Microsoft Graph.

### Identity and access | Identity and sign-in
You can now configure the Microsoft Entra ID [certificate-based authentication (CBA)](/graph/api/resources/x509CertificateAuthenticationMethodConfiguration?view=graph-rest-beta&preserve-view=true) policy to [send hints back to the client application](/graph/api/resources/x509certificateissuerhintsconfiguration?view=graph-rest-beta&preserve-view=true) that filters the certificates shown in the certificate picker when the user initiates sign-in using a certificate.

### Identity and access | Partner customer administration
When [creating](/graph/api/tenantrelationship-post-delegatedadminrelationships?view=graph-rest-beta&preserve-view=true) a [delegated admin relationship](/graph/api/resources/delegatedAdminRelationship?view=graph-rest-beta&preserve-view=true) between a partner and customer, set the duration by which the validity of the relationship is automatically extended. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=dc7a0ac7-c74b-4473-84d8-47e35c796ce3)_.

### Reports
The audit trail of all HTTP requests that Microsoft Graph received and processed for your tenant are now available through **Microsoft Graph activity logs**. Use Azure Monitor Logs to collect the logs and configure downstream destinations such as Azure Storage or stream with Azure Event Hubs to external security information and event management (SIEM) tools. For more information about Microsoft Graph activity logs, see [Access Microsoft Graph activity logs (preview)](/graph/microsoft-graph-activity-logs-overview).

### Security | Attack simulation and training
Create an [attack simulation](/graph/api/resources/simulation?view=graph-rest-beta&preserve-view=true) campaign with [landing page](/graph/api/resources/landingpage?view=graph-rest-beta&preserve-view=true), [login page](/graph/api/resources/loginpage?view=graph-rest-beta&preserve-view=true), [training](/graph/api/resources/training?view=graph-rest-beta&preserve-view=true), and [endUserNotifications](/graph/api/resources/endusernotification?view=graph-rest-beta&preserve-view=true). _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=3984db43-19bc-4257-bfc2-38c30d8462f3)_.

### Security | Records management
Support app scenarios to read any [retention event](/graph/api/resources/security-retentionevent?view=graph-rest-beta&preserve-view=true), [retention event type](/graph/api/resources/security-retentioneventtype?view=graph-rest-beta&preserve-view=true), and [retention label](/graph/api/resources/security-retentionlabel?view=graph-rest-beta&preserve-view=true) without a signed-in user. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=a8aa5b98-5fb3-4aba-acec-5e85209a4026)_.

### Teamwork and communications | Calls and online meetings 
- Get a [call recording](/graph/api/resources/callRecording?view=graph-rest-beta&preserve-view=true) or [call transcript](/graph/api/resources/calltranscript?view=graph-rest-beta&preserve-view=true) that includes more identity information for the organizer, in addition to the existing meeting organizer ID for the [online meeting](/graph/api/resources/onlinemeeting?view=graph-rest-beta&preserve-view=true). Additional identity information may include data such as user display name, identity type, or tenant ID. _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=8a566519-e115-4081-8f15-bc92112e8d64)_.
- Get the preferred display name of a [participant](/graph/api/resources/participant?view=graph-rest-beta&preserve-view=true) in a [call](/graph/api/resources/call?view=graph-rest-beta&preserve-view=true). _See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=840dd994-b26b-48a2-8d7c-1b52ea86a45c)_.

### Workbooks and charts
Get tasks that a user has identified in association with a [comment](/graph/api/resources/workbookcomment?view=graph-rest-beta&preserve-view=true) or [reply for a comment](/graph/api/resources/workbookcommentreply?view=graph-rest-beta&preserve-view=true) in a [worksheet](/graph/api/resources/workbookWorksheet?view=graph-rest-beta&preserve-view=true):
- [List](/graph/api/workbookworksheet-list-tasks?view=graph-rest-beta&preserve-view=true) [document tasks](/graph/api/resources/workbookDocumentTask?view=graph-rest-beta&preserve-view=true) on a worksheet. 
- [List](/graph/api/workbookdocumenttask-list-changes?view=graph-rest-beta&preserve-view=true) the [changes of a document task](/graph/api/resources/workbookdocumenttaskchange?view=graph-rest-beta&preserve-view=true).

_See the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=5472d980-5acf-4663-b1af-c7d22e28d1b3)_.


## Want to stay in the loop?

Here are some ways we can engage:

- Are there scenarios you'd like Microsoft Graph to support? Suggest and vote for new features at [Microsoft Feedback Portal](https://aka.ms/graphfeedback).
    Some new features originate as popular requests from the developer community. The Microsoft Graph team regularly evaluates customer needs and releases new features in the following order:

    1. Debut in **_preview_** status. Any related REST API updates are in the beta endpoint (`https://graph.microsoft.com/beta`).  

    2. Promoted to **_general availability_ (GA)** status, if sufficient feedback indicates viability. Any related REST API updates are added to the v1.0 endpoint (`https://graph.microsoft.com/v1.0`). 
- Be an active member in the Microsoft Graph community! [Join](https://aka.ms/m365-dev-call) the weekly Microsoft 365 platform community call.
- Sign up for the [Microsoft 365 developer program](https://developer.microsoft.com/office/dev-program), get a free Microsoft 365 subscription, and start developing!


## See also
- Check out the [Microsoft Graph developer blog](https://developer.microsoft.com/graph/blogs/) periodically for release announcements and helpful resources.
- Browse details of Microsoft Graph API additions, and API behavior updates in the [changelog](https://developer.microsoft.com/graph/changelog/).
- Find [highlights of earlier releases](whats-new-earlier.md).
- Learn more about [versioning, support, and breaking change policies for Microsoft Graph](versioning-and-support.md).
