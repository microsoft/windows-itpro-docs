---
title: UWF_OverlayConfig.SetMaximumSize
description: UWF_OverlayConfig.SetMaximumSize
ms.date: 05/20/2024
ms.topic: reference
---

# UWF_OverlayConfig.SetMaximumSize

Sets the maximum cache size of the Unified Write Filter (UWF) overlay.

## Syntax

```powershell
UInt32 SetMaximumSize(
    UInt32 size
);
```

## Parameters

**size**</br>An integer that represents the maximum cache size, in megabytes, of the overlay.

## Return Value

Returns an HRESULT value that indicates [WMI status](/windows/win32/wmisdk/wmi-non-error-constants) or a [WMI error](/windows/win32/wmisdk/wmi-error-constants).

## Remarks

When the size of the overlay reaches the *size* value, UWF returns an error for any attempt to write to a protected volume.

If the overlay type is disk-based, your device must meet the following requirements to change the maximum size of the overlay.

- UWF must be disabled in the current session.
- The *size* value must be at least 1024.
- The system volume on your device must have available free space greater than the new maximum size value.

If the overlay type is RAM-based, your device must meet the following requirement to change the maximum size of the overlay.

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
- [Unified Write Filter]( index.md)
