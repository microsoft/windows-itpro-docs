---
title: UWF_Volume.CommitFileDeletion
description: UWF_Volume.CommitFileDeletion
ms.date: 05/20/2024
ms.topic: reference
---

# UWF_Volume.CommitFileDeletion

Deletes the specified file and commits the deletion to the physical volume.

## Syntax

```powershell
UInt32 CommitFileDeletion(
    string FileName
);
```

## Parameters

**FileName**</br>\[in\] A string that contains the path of the file to delete, but does not include the drive letter or volume name. For example: “\\users\\test.dat”.

## Return Value

Returns an HRESULT value that indicates [WMI status](/windows/win32/wmisdk/wmi-non-error-constants) or a [WMI error constant](/windows/win32/wmisdk/wmi-error-constants).

## Remarks

The *FileName* must contain the name of a file that exists on the physical volume. The **CommitFileDeletion** method cannot delete a file that does not exist.

You must use an administrator account to call this method.

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
