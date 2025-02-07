---
title: UWF_OverlayConfig.SetType
description: UWF_OverlayConfig.SetType
ms.date: 05/20/2024
ms.topic: reference
---

# UWF_OverlayConfig.SetType

Sets the type of the Unified Write Filter (UWF) overlay to either RAM-based or disk-based.

## Syntax

```powershell
UInt32 SetType(
    UInt32 type
);
```

## Parameters

**type**</br>The type of overlay. Set to **0** for a RAM-based overlay; set to **1** for a disk-based overlay.

## Return Value

Returns an HRESULT value that indicates [WMI status](/windows/win32/wmisdk/wmi-non-error-constants) or a [WMI error](/windows/win32/wmisdk/wmi-error-constants).

## Remarks

Changes to the overlay type take effect during the next device restart in which UWF is enabled.

When you change the overlay type from RAM-based to disk-based, UWF creates a file on the system volume. The file has a size equal to the **MaximumSize** property of [UWF_OverlayConfig](uwf-overlayconfig.md).

Before you can change the overlay type to disk-based, your device must meet the following requirements.

- UWF must be disabled in the current session.
- The system volume on your device must have available free space greater than the maximum size of the overlay.
- The maximum size of the overlay must be at least 1024 MB.

Before you can change the overlay type to RAM-based, your device must meet the following requirements.

- UWF must be disabled in the current session.

## Requirements

| Windows Edition        | Supported |
|:-----------------------|:---------:|
| Windows Home           | No        |
| Windows Pro            | No        |
| Windows Enterprise     | Yes       |
| Windows Education      | Yes       |
| Windows IoT Enterprise | Yes       |

## Related articles

- [UWF_OverlayConfig](uwf-overlayconfig.md)
- [Overlay for Unified Write Filter (UWF)](uwfoverlay.md)
- [Unified Write Filter]( index.md)
