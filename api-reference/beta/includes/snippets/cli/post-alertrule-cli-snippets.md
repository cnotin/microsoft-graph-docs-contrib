---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc-beta device-management monitoring alert-rules create --body '{\
  "id": "215c55cc-b1c9-4d36-a870-be5778101714",\
  "displayName": "Azure network connection failure impacting Cloud PCs",\
  "severity": "informational",\
  "isSystemRule": true,\
  "description": "Azure network connection checks have failed and is potentially impacting existing Cloud PCs and blocking the provisioning of new Cloud PCs",\
  "enabled": true,\
  "alertRuleTemplate": "cloudPcOnPremiseNetworkConnectionCheckScenario",\
  "threshold": {\
      "aggregation": "count",\
      "operator": "greaterOrEqual",\
      "target": 90\
  },\
  "notificationChannels": [\
      {\
        "notificationChannelType": "portal",\
        "notificationReceivers": []\
      },\
      {\
        "notificationChannelType": "email",\
        "notificationReceivers": [\
            {\
                "locale": "en-us",\
                "contactInformation": "serena.davis@contoso.com"\
            }\
        ]\
      }\
  ]\
}\
'

```