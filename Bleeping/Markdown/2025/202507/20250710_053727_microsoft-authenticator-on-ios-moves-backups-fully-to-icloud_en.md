# Microsoft Authenticator on iOS moves backups fully to iCloud

![Microsoft](https://www.bleepstatic.com/content/hl-images/2024/10/04/Microsoft.jpg)

Microsoft is rolling out a new backup system in September for its Authenticator app on iOS, removing the requirement to use a Microsoft personal account to back up TOTP secrets and account names.

Previously, the Microsoft Authenticator app required iOS users to sign in with a personal Microsoft Account to enable backups, regardless of whether they were using the app for personal or enterprise credentials.

This created problems in enterprise environments where organizations often like to keep personal and corporate data separated.

The new backup system will continue to use the signed-in iCloud account to store the backups, but no longer with the requirement to use a Microsoft account. If the company uses a managed Apple ID on their corporate devices, then that will be used instead of a personal account.

Microsoft says this new feature will begin rolling out in September and will be finished by early October 2025, with users being shown a notification about the new experience in the app, as shown below.

![In-app warning about upcoming change](https://www.bleepstatic.com/images/news/Microsoft/m/microsoft-authenticator/ios-backups/microsoft-authenticator-ios-backup.png)

**In-app warning about upcoming change**  
_Source: Microsoft_

Microsoft says this feature will only be available to users running iOS 16.0 or later with iCloud and iCloud Keychain enabled. Once installed, account names and TOTP credentials (secrets) will be backed up to iCloud and restored automatically on new devices when you use the same Apple account.

"Account names for all accounts in the Authenticator app—including work or school accounts, Microsoft personal accounts, and non-Microsoft accounts (such as Amazon, Google)—will be securely backed up using iCloud and iCloud Keychain," reads the Microsoft announcement.

The company stresses that only TOTP secrets will be backed up and no other credentials, and that users can disable the backup feature through the iCloud settings on their device.

Microsoft says that this feature will automatically roll out to all users with no admin action required.

The feature comes after Microsoft's [recent announcement](https://www.bleepingcomputer.com/news/security/microsoft-ends-authenticator-password-autofill-moves-users-to-edge/) they are removing the password autofill and management functionality from Authenticator.