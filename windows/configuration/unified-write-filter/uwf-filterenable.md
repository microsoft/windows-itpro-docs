---
title: UWF_Filter.Enable
description: UWF_Filter.Enable
ms.date: 05/20/2024
ms.topic: reference
---

# UWF_Filter.Enable

Enables Unified Write Filter (UWF) on the next restart.

## Syntax

```powershell
UInt32 Enable();
```

## Parameters

None.

## Return Value

Returns an HRESULT value that indicates [WMI status](/windows/win32/wmisdk/wmi-non-error-constants) or a [WMI error](/windows/win32/wmisdk/wmi-error-constants).

## Remarks

You must use an administrator account to enable UWF.

You must restart your device after you enable or disable UWF before the change takes effect.

The first time you enable UWF on your device, UWF makes the following changes to your system to improve the performance of UWF:

- Paging files are disabled.
- System restore is disabled.
- SuperFetch is disabled.
- File indexing service is turned off.
- Defragmentation service is turned off.
- Fast boot is disabled.
- BCD setting **bootstatuspolicy** is set to **ignoreallfailures**.

You can change these settings after you enable UWF if you want to. For example, you can move the page file location to an unprotected volume and re-enable paging files.

Additionally, after you run `uwfmgr filter enable`, restart the computer and exit the servicing mode, the following things are disabled:

- Windows Update by setting `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU\NoAutoUpdate`
- Windows Store Update by setting `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\WindowsStore\AutoDownload`
- Registry Reorganization by setting `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Session Manager\Configuration Manager\RegistryReorganizationLimitDays`
- Maintenance Hour by setting `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\Maintenance\MaintenanceDisabled`

After you run `uwfmgr filter disable`, restart the computer and enter the serving mode, the changes are reverted.

## Requirements

| Windows Edition        | Supported |
|:-----------------------|:---------:|
| Windows Home           | No        |
| Windows Pro            | No        |
| Windows Enterprise     | Yes       |
| Windows Education      | Yes       |
| Windows IoT Enterprise | Yes       |

## Related articles

- [UWF_Filter](uwf-filter.md)
- [Unified Write Filter]( index.md)
