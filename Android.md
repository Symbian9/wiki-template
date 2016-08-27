# Difference between mobile platform and desktop version

* Screen size
* Screen resolution
* Touch control instead of mouse + keyboard
* Non-traditional file storage

# File storage

# Requirements and Storage Options

Mapper needs to use a storage which
- allows for big amounts of data (background templates!)
- will not be deleted when uninstalling the app
- is available offline
- is accessible for file transfer from the PC.

These requirements are fulfilled by Android's "External Storage" which is also officially recommended "for large data sets that are not private". There are four other options which are incompatible with Mapper's requirements: Shared Preferences (not for big amounts of data), Internal Storage (removed on uninstalling), SQLite Databases (not accessible for file transfer) and Network Connection (not available offline, and maybe slow for big data).

*Cf. https://developer.android.com/guide/topics/data/data-storage.html*

## External Storage on Android

*Cf. https://source.android.com/devices/storage/*

- Traditional storage
  - Portable storage: a physical media, such as an SD card (since Android 1.0) or USB device (since Android 6.0)
  - Emulated storage: a portion of the internal (unremovable) storage, exposed through an emulation layer (since Android 3.0)
- Adoptable storage (since Android 6.0):
  provided by physical media, like an SD card or USB, but encrypted and formatted to behave like internal storage, and thus tied to a particular device.

So although called "external", this storage may include emulated storage which actually resides on internal storage.

Full write access to external storage (including read access) is subject to the `WRITE_EXTERNAL_STORAGE` permission (since Android 1.0). Pure read access became possible with the `READ_EXTERNAL_STORAGE` permission (since Android 4.1).

Android 4.4 introduced an implicit permission for apps to access data in /Android/data/PACKAGENAME (on each external storage volume).

Android 6.0 introduced interactive permission granting at runtime, i.e. the explicit `WRITE_EXTERNAL_STORAGE` maybe granted or revoked by the user as needed, instead of being accepted at installation. Use may even revoke permissions from apps developed for older versions.

## How Mapper finds maps

Given the `WRITE_EXTERNAL_STORAGE` permission, Mapper is able read from and to write to external storage. The first prototype of Mapper for Android tried to find external storage in a few fixed locations. This quickly turned out to be insufficient because different devices used different path to provide emulated or portable storage. So Mapper was modified to lookup relevant locations via the Android API. So Mapper 0.6.4 looks for a folder named `OOMapper` in the following locations:
- the location given in the environment variable `EXTERNAL_STORAGE`
- all locations given in the environment variable `SECONDARY_STORAGE` (separated by `:`)

If this folder was not found in the previous locations, it continues with the following ones (serving as a fallback):
- `/`
- `/mnt`
- `/mnt/sdcard`
- `/sdcard`
- `/storage`

All map files found in OOMapper folders in the examined locations are displayed to the user.