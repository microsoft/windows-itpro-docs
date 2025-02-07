---
title: UWF_Servicing.UpdateWindows
description: UWF_Servicing.UpdateWindows
ms.date: 05/20/2024
ms.topic: reference
---

# UWF_Servicing.UpdateWindows

Calls Windows Update to download and install critical and security updates for your device running Windows 10 Enterprise.

## Syntax

```powershell
UInt32 UpdateWindows(
    [out] UInt32 UpdateStatus
);
```

## Parameters

**UpdateStatus**</br>\[out\] An integer that contains the status of the Windows Update operation, according to the following table:

| UpdateStatus     | Description       |
|:----------------:|-------------------|
| 0                | Success.          |
| 3010             | Restart required. |
| Any other value. | Generic error.    |

## Return Value

Returns an HRESULT value that indicates [WMI status](/windows/win32/wmisdk/wmi-non-error-constants) or a [WMI error](/windows/win32/wmisdk/wmi-error-constants).

## Remarks

This method is meant to be used as part of a servicing script. For more information, see [Service UWF-protected devices](service-uwf-protected-devices.md).

This method does not disable or enable Unified Write Filter (UWF). If you call this method while UWF is enabled, updates may be lost when the device restarts.

## Requirements

| Windows Edition        | Supported |
|:-----------------------|:---------:|
| Windows Home           | No        |
| Windows Pro            | No        |
| Windows Enterprise     | Yes       |
| Windows Education      | Yes       |
| Windows IoT Enterprise | Yes       |

## Related articles

- [UWF_Servicing](uwf-servicing.md)
- [Unified Write Filter]( index.md)
