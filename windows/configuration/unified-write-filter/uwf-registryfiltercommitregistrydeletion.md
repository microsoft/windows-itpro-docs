---
title: UWF_RegistryFilter.CommitRegistryDeletion
description: UWF_RegistryFilter.CommitRegistryDeletion
ms.date: 05/20/2024
ms.topic: reference
---

# UWF_RegistryFilter.CommitRegistryDeletion

Deletes the specified registry key or registry value and commits the deletion.

## Syntax

```powershell
UInt32 CommitRegistryDeletion(
    string Registrykey,
    string ValueName
);
```

## Parameters

**RegistryKey**</br>A string that contains the full path of the registry key that contains the value to be deleted. If *ValueName* is empty, the entire registry key is deleted.

**ValueName**</br>A string that contains the name of the value to be deleted.

## Return Value

Returns an HRESULT value that indicates [WMI status](/windows/win32/wmisdk/wmi-non-error-constants) or a [WMI error](/windows/win32/wmisdk/wmi-error-constants).

## Remarks

If *ValueName* is specified, this method will delete only the value specified by *ValueName* that is contained by *RegistryKey*. If *ValueName* is empty, the entire *RegistryKey* and all its sub keys are deleted.

This method deletes the registry key or registry value from both the overlay and the persistent storage.

You must use an administrator account to change any properties or call any methods that change the configuration settings.

## Requirements

| Windows Edition        | Supported |
|:-----------------------|:---------:|
| Windows Home           | No        |
| Windows Pro            | No        |
| Windows Enterprise     | Yes       |
| Windows Education      | Yes       |
| Windows IoT Enterprise | Yes       |

## Related articles

- [UWF_RegistryFilter](uwf-registryfilter.md)
- [Unified Write Filter]( index.md)
