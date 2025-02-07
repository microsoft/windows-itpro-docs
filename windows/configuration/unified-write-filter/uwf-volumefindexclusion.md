---
title: UWF_Volume.FindExclusion
description: UWF_Volume.FindExclusion
ms.date: 05/20/2024
ms.topic: reference
---

# UWF_Volume.FindExclusion

Checks if a specific file or folder is in the exclusion list for a volume protected by Unified Write Filter (UWF).

## Syntax

```powershell
UInt32 FindExclusion (
    [in] string FileName,
    [out] boolean bFound
);
```

## Parameters

**FileName**</br>\[in\] A string that contains the full path of the file or folder relative to the volume.

**bFound**</br>\[out\] Indicates if *FileName* is in the file exclusion list for the volume.

## Return Value

Returns an HRESULT value that indicates [WMI status](/windows/win32/wmisdk/wmi-non-error-constants) or a [WMI error constant](/windows/win32/wmisdk/wmi-error-constants).

## Remarks

**FindExclusion** sets *bFound* to **true** only for file and folder exclusions that have been explicitly added to the exclusion list. Files and subfolders that are in an excluded folder are not identified as excluded by **FindExclusion**, unless they have been explicitly excluded.

## Requirements

| Windows Edition        | Supported |
|:-----------------------|:---------:|
| Windows Home           | No        |
| Windows Pro            | No        |
| Windows Enterprise     | Yes       |
| Windows Education      | Yes       |
| Windows IoT Enterprise | Yes       |

## Related articles

- [UWF_Volume](uwf-volume.md)
- [Unified Write Filter]( index.md)
