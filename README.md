**These policies are in active development and so might contain changes that do not work with current versions of Thunderbird.**

**You should use the officially released versions (https://github.com/drlellinger/thunderbird-policies/releases) if you are deploying changes.**

Policies can be specified using the Group Policy templates on Windows (https://github.com/drlellinger/thunderbird-policies/tree/master/windows)

| Policy Name | Description
| --- | --- |
| **[`AppUpdateURL`](#AppUpdateURL)** | Change the URL for application update.
| **[`BlockAboutAddons`](#blockaboutaddons)** | Block access to the Add-ons Manager (about:addons).
| **[`BlockAboutConfig`](#blockaboutconfig)** | Block access to about:config. (Bug fixed with TB 68.1.1)
| **[`BlockAboutProfiles`](#blockaboutprofiles)** | Block access to about:profiles.
| **[`Certificates`](#certificates)** |
| **[`Certificates -> ImportEnterpriseRoots`](#certificates--importenterpriseroots)** | Trust certificates that have been added to the operating system certificate store by a user or administrator.
| **[`Certificates -> Install`](#certificates--install)** | Install certificates into the Thunderbird certificate store.
| **[`DisableAppUpdate`](#disableappupdate)** | Turn off application updates.
| **[`DisableDeveloperTools`](#disabledevelopertools)** | Remove access to all developer tools.
| **[`DisableMasterPasswordCreation`](#disablemasterpasswordcreation)** | Remove the master password functionality.
| **[`Extensions`](#extensions)** | Control the installation, uninstallation and locking of extensions.
| **`ExtensionSettings`** | Manage all aspects of extensions.
| **[`ExtensionUpdate`](#extensionupdate)** | Control extension updates.

### AppUpdateURL

Change the URL for application update.

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `app.update.url`

#### Windows
```
Software\Policies\Mozilla\Thunderbird\AppUpdateURL = "https://yoursite.com"
```
### BlockAboutAddons

Block access to the Add-ons Manager (about:addons).

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** `disableAddonsManager`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Mozilla\Thunderbird\BlockAboutAddons = 0x1 | 0x0
```
### BlockAboutConfig

Block access to about:config.

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** `disableAboutConfig`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Mozilla\Thunderbird\BlockAboutConfig = 0x1 | 0x0
```
### BlockAboutProfiles

Block access to About Profiles (about:profiles).

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** `disableAboutProfiles`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Mozilla\Thunderbird\BlockAboutProfiles = 0x1 | 0x0
```
### Certificates | Install

Install certificates into the Thunderbird certificate store. If only a filename is specified, Thunderbird searches for the file in the following locations:

- Windows
  - %USERPROFILE%\AppData\Local\Thunderbird\Certificates
  - %USERPROFILE%\AppData\Roaming\Thunderbird\Certificates

Certificates are installed using the trust string `CT,CT,`.

Binary (DER) and ASCII (PEM) certificates are both supported.

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** `certs.ca`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Mozilla\Thunderbird\Certificates\Install\1 = "cert1.der"
Software\Policies\Mozilla\Thunderbird\Certificates\Install\2 = "C:\Users\username\cert2.pem"
```
### DisableAppUpdate
Turn off application updates.

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** `disableThunderbirdUpdates`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Mozilla\Thunderbird\DisableAppUpdate = 0x1 | 0x0
```
### DisableDeveloperTools
Remove access to all developer tools.

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** `removeDeveloperTools`\
**Preferences Affected:** `devtools.policy.disabled`

#### Windows
```
Software\Policies\Mozilla\Thunderbird\DisableDeveloperTools = 0x1 | 0x0`
```
### DisableMasterPasswordCreation
Remove the master password functionality.

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** `noMasterPassword`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Thunderbird\Thunderbird\DisableMasterPasswordCreation = 0x1 | 0x0
```
### Extensions
Control the installation, uninstallation and locking of extensions.

`Install` is a list of URLs or native paths for extensions to be installed. 

`Uninstall` is a list of extension IDs that should be uninstalled if found.

`Locked` is a list of extension IDs that the user cannot disable or uninstall.

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** `addons`\
**Preferences Affected:** N/A

#### Windows
```
Software\Policies\Mozilla\Thunderbird\Extensions\Install\1 = "//path/to/xpi"
Software\Policies\Mozilla\Thunderbird\Extensions\Uninstall\1 = "bad_addon_id@mozilla.org"
Software\Policies\Mozilla\Thunderbird\Extensions\Locked\1 = "addon_id@mozilla.org"
```
### ExtensionUpdate
Control extension updates.

**Compatibility:** Thunderbird 68\
**CCK2 Equivalent:** N/A\
**Preferences Affected:** `extensions.update.enabled`

#### Windows
```
Software\Policies\Mozilla\Thunderbird\ExtensionUpdate = 0x1 | 0x0
```
