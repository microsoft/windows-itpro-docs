---
title: Privacy
description: This article provides details about the data platform and privacy compliance for Autopatch
ms.date: 09/16/2024
ms.service: windows-client
ms.subservice: autopatch
ms.topic: concept-article
ms.localizationpriority: medium
author: tiaraquan
ms.author: tiaraquan
manager: aaroncz
ms.reviewer: hathind
ms.collection:
  - highpri
  - tier1
---

# Privacy

Windows Autopatch is a cloud service for enterprise customers designed to keep Windows devices updated. This article provides details about data platform and privacy compliance for Windows Autopatch.

## Windows Autopatch data sources and purpose

Autopatch collects and stores data according to the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839).

### [Business Premium and A3+](#tab/data-sources-forbusiness-premium-a3-data-sources)

Data provided by the customer or generated by the service during normal operation is stored. For example, when a device is targeted with a policy, information is stored enabling the service to deliver content to targeted devices.

Business Premium and A3+ licenses require the use of Windows Diagnostic data. For more information, see [Diagnostic data in Windows Autopatch](#microsoft-windows-1011-diagnostic-data).

### [Windows Enterprise E3+ and F3](#tab/windows-enterprise-e3-f3-data-sources)

When you've [activated Windows Autopatch features](../prepare/windows-autopatch-feature-activation.md), data from various sources is used to properly administer enrolled devices and monitor that the service is working properly.

The sources include Microsoft Entra ID, Microsoft Intune, and Microsoft Windows 10/11. The sources provide a comprehensive view of the devices that Windows Autopatch manages.

| Data source | Purpose |
| ---- | ---- |
| [Microsoft Windows 10/11 Enterprise](/windows/windows-10/) | Management of device setup experience, managing connections to other services, and operational support for IT pros. |
| [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) | Uses Windows 10/11 Enterprise diagnostic data to provide additional information on Windows 10/11 update. |
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) | Device management and to keep your data secure. The following endpoint management data sources are used:<br><ul><li>[Microsoft Entra ID](/entra/identity/): Authentication and identification of all user accounts.</li><li>[Microsoft Intune](/mem/intune/): Distributing device configurations, device management and application management.</li></ul> |
| [Windows Autopatch](https://go.microsoft.com/fwlink/?linkid=2109431) | Data provided by the customer or generated by the service during running of the service. |
| [Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/enterprise/compare-office-365-plans)| Management of Microsoft 365 Apps. |

---

## Windows Autopatch data process and storage

[!INCLUDE [windows-autopatch-applies-to-all-licenses](../includes/windows-autopatch-applies-to-all-licenses.md)]

Windows Autopatch relies on data from multiple Microsoft products and services to provide its service to enterprise customers.
To protect and maintain enrolled devices, we process and copy data from these services to Windows Autopatch. When we process data, we follow the documented directions you provide as referenced in the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) and [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).

Processor duties of Windows Autopatch include ensuring appropriate confidentiality, security, and resilience. Windows Autopatch employs additional privacy and security measures to ensure proper handling of personal identifiable data.

## Windows Autopatch data storage and staff location

Data obtained by Windows Autopatch and other services are required to keep the service operational. If a device is removed from Windows Autopatch, we keep data for a maximum of 30 days. For more information on data retention, see [Data retention, deletion, and destruction in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

### [Business Premium and A3+](#tab/business-premium-a3-data-storage)

Data stored in this part of the service is stored only in two regions, either Azure’s north American data centers or its European ones.

### [Windows Enterprise E3+ and F3](#tab/windows-enterprise-e3-f3-data-storage)

Windows Autopatch stores its data in the Azure data centers based on your data residency. For more information, see [Microsoft 365 data center locations](/microsoft-365/enterprise/o365-data-locations).

The Windows Autopatch Service Engineering Team is in the United States, India, and Romania.

---

## Microsoft Windows 10/11 diagnostic data

Windows Autopatch uses Windows diagnostic data to keep Windows secure, up to date, fix problems, and make product improvements. Learn more about configuring diagnostic data for your organization in Intune.

### [Business Premium and A3+](#tab/business-premium-a3-diagnostic-data)

To take advantage of the unique deployment scheduling controls and protections tailored to your population and to [deploy driver updates](/windows/deployment/update/deployment-service-drivers), devices must share diagnostic data with Microsoft. For these features, at minimum, the deployment service requires devices to send [diagnostic data](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#diagnostic-data-settings) at the *Required* level for these features.

### [Windows Enterprise E3+ and F3](#tab/windows-enterprise-e3-f3-diagnostic-data)

When you've [activated Windows Autopatch features](../prepare/windows-autopatch-feature-activation.md), Windows Autopatch creates the “Windows Autopatch – Data Collection Policy” and assigns it to enrolled devices. This policy configures the following settings:

| Setting | Value | Description |
| --- | --- | --- |
| Allow telemetry | Optional. This value was previously named “**Full**” for Windows 10 devices. For more information, see [Changes to Windows diagnostic data collection](/previous-versions/windows/it-pro/privacy/changes-to-windows-diagnostic-data-collection). | Allow the device to send diagnostic and usage telemetry data, such as Watson. For more information about diagnostic data, including what is and what isn't collected by Windows, see [diagnostic data settings](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#diagnostic-data-settings). |
| Limit Diagnostic Log Collection | Enabled | This policy setting specifies whether diagnostic log data can be collected when more information is needed to troubleshoot a problem. |
| Limit Dump Collection | Enabled | This policy setting limits the type of dumps that can be collected when more information is needed to troubleshoot a problem. These dumps aren't sent unless we have permission to collect optional diagnostic data. By enabling this policy setting, Windows Error Reporting is limited to sending kernel mini dumps and user mode triage dumps only. |
| Limit Enhanced Diagnostic Data Windows Analytics | Enabled | This policy setting, in combination with the Allow Telemetry policy setting, enables organizations to send Microsoft a specific set of diagnostic data for IT insights via Windows Analytics services. |
| Allow Windows Autopatch Processing | Allowed | Allows diagnostic data from this device to be processed by Windows Autopatch. |

Windows Autopatch only processes and stores system-level data from Windows 10/11 optional diagnostic data that originates from enrolled devices such as application and device reliability, and performance information. Windows Autopatch doesn't process and store customers' data such as chat and browser history, voice, text, or speech data.

For more information about the diagnostic data collection of Microsoft Windows 10/11, see the [Where we store and process data section](https://privacy.microsoft.com/en-US/privacystatement#mainwherewestoreandprocessdatamodule) of the Microsoft Privacy Statement.

For more information about how Windows diagnostic data is used, see:

- [Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enable-windows-diagnostic-data-processor-configuration)
- [Features that require Windows diagnostic data](/mem/intune/protect/data-enable-windows-data)

---

## Tenant access

### [Business Premium and A3+](#tab/business-premium-a3-tenant-access)

[!INCLUDE [windows-autopatch-business-premium-a3-licenses](../includes/windows-autopatch-business-premium-a3-licenses.md)]

### [Windows Enterprise E3+ and F3 licenses](#tab/windows-enterprise-e3-f3-tenant-access)

For more information about tenant access and changes made to your tenant upon activating Windows Autopatch features, see [Changes made at feature activation](../references/windows-autopatch-changes-made-at-feature-activation.md).

---

## Microsoft Windows Update for Business Reports

### [Business Premium and A3+](#tab/business-premium-a3-wufb-reports)

If you have Business Premium and A3+ licenses, when you use [Windows Update for Business reports](/windows/deployment/update/wufb-reports-overview), using diagnostic data at the following levels allows device names to appear in reporting:

- *Optional* level (previously Full) for Windows 11 devices
- *Enhanced* level for Windows 10 devices

### [Windows Enterprise E3+ and F3](#tab/windows-enterprise-e3-f3-wufb-reports)

Windows Update for Business uses data from Windows diagnostics to analyze update status and failures. When you [activate Windows Autopatch features](../prepare/windows-autopatch-feature-activation.md), this data is used to deliver reports and confirm that registered devices are up to date.

---

## Microsoft Entra ID

[!INCLUDE [windows-autopatch-applies-to-all-licenses](../includes/windows-autopatch-applies-to-all-licenses.md)]

Identifying data used by Windows Autopatch is stored by Microsoft Entra ID in a geographical location. The geographical location is based on the location provided by the organization upon subscribing to Microsoft online services, such as Microsoft Apps for Enterprise and Azure. For more information on where your Microsoft Entra data is located, see [Microsoft Entra ID - Where is your data located?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

## Microsoft Intune

[!INCLUDE [windows-autopatch-applies-to-all-licenses](../includes/windows-autopatch-applies-to-all-licenses.md)]

Microsoft Intune collects, processes, and shares data to Windows Autopatch to support business operations and services. For more information about the data collected in Intune, see [Data collection in Intune](/mem/intune/protect/privacy-data-collect).

For more information on Microsoft Intune data locations, see [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations). Intune respects the storage location selections made by the administrator for customer data.

## Microsoft 365 Apps for enterprise

### [Business Premium and A3+](#tab/business-premium-a3-microsoft-365)

Microsoft 365 Apps for enterprise only collects and shares data with Windows Autopatch when you [activate Windows Autopatch features](../prepare/windows-autopatch-feature-activation.md). Windows Autopatch ensure those apps are up to date with the latest version.

To use Windows Autopatch features, you must have the correct Enterprise license(s) and [activate Windows Autopatch features](../prepare/windows-autopatch-feature-activation.md). For more information about Enterprise licenses and the prerequisites, see [Windows Autopatch prerequisites](../prepare/windows-autopatch-prerequisites.md). For more information about features and capabilities, see [Features and capabilities](../overview/windows-autopatch-overview.md#features-and-capabilities).

### [Windows Enterprise E3+ and F3](#tab/windows-enterprise-e3-f3-microsoft-365)

Microsoft 365 Apps for enterprise collects and shares data with Windows Autopatch to ensure those apps are up to date with the latest version. These updates are based on predefined update channels managed by Windows Autopatch. For more information on Microsoft 365 Apps's data collection and storage locations, see [Microsoft Defender for Endpoint data storage and privacy](/microsoft-365/enterprise/o365-data-locations).

---

## Major data change notification

[!INCLUDE [windows-autopatch-applies-to-all-licenses](../includes/windows-autopatch-applies-to-all-licenses.md)]

We notify customers through the Microsoft 365 message center, and the Windows Autopatch admin center about security incidents and major changes to the service.

Changes to the types of data gathered and storage are considered a material change. We provide a minimum of 30 days advanced notice of this change as it's standard practice for Microsoft 365 products and services.

## Data subject requests

Windows Autopatch follows General Data Protection Regulation (GDPR) and California Consumer Privacy Act (CCPA) privacy regulations, which give data subjects specific rights to their data.

These rights include:

- Obtaining copies of data
- Requesting corrections to it
- Restricting the processing of it
- Deleting it
- Receiving it in an electronic format so it can be moved to another controller

For more general information about Data Subject Requests (DSRs), see [Data Subject Requests and the GDPR and CCPA](/compliance/regulatory/gdpr-data-subject-requests).

### [Business Premium and A3+](#tab/business-premium-a3-data-subjects)

For Data Subject Requests from other products related to the service, see the following articles:

- [Windows diagnostic data](/compliance/regulatory/gdpr-dsr-windows)
- [Microsoft Intune data](/compliance/regulatory/gdpr-dsr-intune)
- [Microsoft Entra data](/compliance/regulatory/gdpr-dsr-azure)

### [Windows Enterprise E3+ and F3](#tab/windows-enterprise-e3-f3-data-subjects)

To exercise data subject requests on data collected by the Windows Autopatch case management system, see the following data subject requests:

| Data subject requests | Description |
| --- | --- |
| Data from Windows Autopatch support requests | Your IT administrator can request deletion, or extraction of data related support requests by submitting a report request in the [admin center](https://go.microsoft.com/fwlink/?linkid=2109431). Provide the following information:<ul><li>Request type: Change request</li><li>Category: Security</li><li>Subcategory: Other</li><li>Description: Provide the relevant device names or usernames</li></ul> |

---

## Legal

[!INCLUDE [windows-autopatch-applies-to-all-licenses](../includes/windows-autopatch-applies-to-all-licenses.md)]

The following is Microsoft's privacy notice to end users of products provided by organizational customers.

The [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement) notifies end users that when they sign into Microsoft products with a work account:

1. Their organization can control and administer their account (including controlling privacy-related settings), and access and process their data.
2. Microsoft might collect and process the data to provide the service to the organization and end users.
