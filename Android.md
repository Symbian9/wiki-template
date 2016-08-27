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

Android has different types of external storage, and there may be different volumes.

- Traditional storage
  - Portable storage: a physical media, such as an SD card (since Android 1.0) or USB device (since Android 6.0)
  - Emulated storage: a portion of the internal (unremovable) storage, exposed through an emulation layer (since Android 3.0)
- Adoptable storage (since Android 6.0):
  provided by physical media, like an SD card or USB, but encrypted and formatted to behave like internal storage, and thus tied to a particular device.

So although called "external", this storage may include emulated storage which actually resides on internal storage.

Full write access to external storage (including read access) is subject to the `WRITE_EXTERNAL_STORAGE` permission (since Android 1.0). Pure read access became possible with the `READ_EXTERNAL_STORAGE` permission (since Android 4.1).

[`Environment.getExternalStoragePublicDirectory`](https://developer.android.com/reference/android/os/Environment.html#getExternalStoragePublicDirectory(java.lang.String)) (since Android 2.2) returns a top-level external storage directory for placing files of a particular type.

Android 4.2 added multi-user support. External storage concepts were adjusted in the following way:
- Primary external storage is specific to each user and not accessible for other user. `/sdcard` can be used to access to primary external storage (whether SD card or not). `WRITE_EXTERNAL_STORAGE` grants access to the whole volume.
- For optimization, large OBB files may be shared between multiple users in the `Android/obb` directory.
- On secondary external storage, apps may only write to package-specific directories as allowed by synthesized permissions (see below, although documented as "since Android 4.4").

Android 4.4 introduced synthesized (implicit) permissions for apps to access data in `Android/data/PACKAGENAME`.

Furthermore, Android 4.4 added a [Storage Access Framework (SAF)](https://developer.android.com/guide/topics/providers/document-provider.html) which aims to standardize the way user access documents in apps. Via a system UI, it gives access to any directory on a storage volume.

A third noteworthy addition is the standard directory for documents, [`DIRECTORY_DOCUMENTS`](https://developer.android.com/reference/android/os/Environment.html#DIRECTORY_DOCUMENTS).

Android 6.0 introduced interactive permission granting at runtime, i.e. the explicit `WRITE_EXTERNAL_STORAGE` maybe granted or revoked by the user as needed, instead of being accepted at installation. Use may even revoke permissions from apps developed for older versions.

Android 7.0 adds [Scoped Directory Access](https://developer.android.com/training/articles/scoped-directory-access.html). A new class [`StorageVolume`](https://developer.android.com/reference/android/os/storage/StorageVolume.html) features a method [`createAccessIntent`](https://developer.android.com/reference/android/os/storage/StorageVolume.html#createAccessIntent(java.lang.String)) for getting runtime access to a standard storage directory or entire (secondary) volume.

## How Mapper 0.6.4 finds maps

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

## Problems and New Approaches for Mapper

- [getExternalStoragePublicDirectory](https://developer.android.com/reference/android/os/Environment.html#getExternalStoragePublicDirectory(java.lang.String))