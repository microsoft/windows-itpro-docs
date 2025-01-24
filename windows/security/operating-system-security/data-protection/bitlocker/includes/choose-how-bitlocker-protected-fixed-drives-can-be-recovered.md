---
author: paolomatarazzo
ms.author: paoloma
ms.date: 10/30/2023
ms.topic: include
---

### Choose how BitLocker-protected fixed drives can be recovered

This policy setting allows you to control how BitLocker-protected fixed data drives are recovered in the absence of the required startup key information. If you enable this policy setting, you can control the methods available to users to recover data from BitLocker-protected fixed data drives. Here are the available options:

- **Allow certificate-based data recovery agent**: specify whether a data recovery agent can be used with BitLocker-protected fixed data drives. Before a data recovery agent can be used, it must be added from the Public Key Policies item in either the Group Policy Management Console or the Local Group Policy Editor
- **Configure user storage of BitLocker recovery information**: select whether users are allowed, required, or not allowed to generate a 48-digit recovery password or a 256-bit recovery key
- **Omit recovery options from the BitLocker setup wizard**: prevent users from specifying recovery options when they turn on BitLocker for a drive. This means that users won't be able to specify which recovery option to use when they turn on BitLocker. BitLocker recovery options for the drive are determined by the policy setting
- **Save BitLocker recovery information to Active Directory Domain Services**: choose which BitLocker recovery information to store in AD DS for fixed data drives. If you select **Backup recovery password and key package**, both the BitLocker recovery password and key package are stored in AD DS. Storing the key package supports recovering data from a drive that has been physically corrupted. If you select **Backup recovery password only**, only the recovery password is stored in AD DS
- **Do not enable BitLocker until recovery information is stored in AD DS for fixed data drives**: prevents users from enabling BitLocker unless the device is connected to the domain and the backup of BitLocker recovery information to AD DS succeeds. When using this option, a recovery password is automatically generated.

> [!IMPORTANT]
> The use of recovery keys must be disallowed if the **Deny write access to fixed drives not protected by BitLocker** policy setting is enabled.

If this policy setting is disabled or not configured, the default recovery options are supported for BitLocker recovery. By default a DRA is allowed, the recovery options can be specified by the user including the recovery password and recovery key, and recovery information is not backed up to AD DS.

For Microsoft Entra hybrid joined devices, the BitLocker recovery password is backed up to both Active Directory and Entra ID.

For Microsoft Entra joined devices, the BitLocker recovery password is backed up to Entra ID.

|  | Path |
|--|--|
| **CSP** | `./Device/Vendor/MSFT/BitLocker/`[FixedDrivesRecoveryOptions](/windows/client-management/mdm/bitlocker-csp#fixeddrivesrecoveryoptions) |
| **GPO** | **Computer Configuration** > **Administrative Templates** > **Windows Components** > **BitLocker Drive Encryption** > **Fixed Data Drives** |
