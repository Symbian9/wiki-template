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

*Cf. https://source.android.com/devices/storage/, https://possiblemobile.com/2014/03/android-external-storage/*

Android has different types of external storage, and there may be different volumes.

- Traditional storage
  - Portable storage: a physical media, such as an SD card (since Android 1.0) or USB device (since Android 6.0)
  - Emulated storage: a portion of the internal (unremovable) storage, exposed through an emulation layer (since Android 3.0)
- Adoptable storage (since Android 6.0):
  provided by physical media, like an SD card or USB, but encrypted and formatted to behave like internal storage, and thus tied to a particular device.

So although called "external", this storage may include emulated storage which actually resides on internal storage.

Since Android 1.0, full access to the external storage given by [`Environment.getExternalStorageDirectory`](https://developer.android.com/reference/android/os/Environment.html#getExternalStorageDirectory()) is subject to the `WRITE_EXTERNAL_STORAGE` permission (since Android 1.0). 

[`Environment.getExternalStoragePublicDirectory`](https://developer.android.com/reference/android/os/Environment.html#getExternalStoragePublicDirectory(java.lang.String)) (since Android 2.2) returns a top-level external storage directory for placing files of a particular type.

Android 4.1 added permission `READ_EXTERNAL_STORAGE` for pure read access tot the external storage.

Android 4.2 added multi-user support. External storage concepts were adjusted in the following way:
- Primary external storage is specific to each user and not accessible for other user. `/sdcard` can be used to access to primary external storage (whether SD card or not). `WRITE_EXTERNAL_STORAGE` grants access to the whole volume.
- For optimization, large OBB files may be shared between multiple users in the `Android/obb` directory.
- On secondary external storage, apps may only write to package-specific directories as allowed by synthesized permissions (see below, although documented as "since Android 4.4").

Android 4.4 introduced synthesized (implicit) permissions for apps to access data in `Android/data/PACKAGENAME`. [`Context.getExternalFilesDirs`](https://developer.android.com/reference/android/content/Context.html#getExternalFilesDirs(java.lang.String)) provides a collection of paths for this folder on all external volumes, starting with the primary storage. However, this folder will be deleted when the app is uninstalled.

Furthermore, Android 4.4 added a [Storage Access Framework (SAF)](https://developer.android.com/guide/topics/providers/document-provider.html) which aims to standardize the way user access documents in apps. Via a system UI, it gives access to any directory on a storage volume.

Another noteworthy addition is the standard directory for documents, [`DIRECTORY_DOCUMENTS`](https://developer.android.com/reference/android/os/Environment.html#DIRECTORY_DOCUMENTS).

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

## Current Situation

- Mapper may not find all relevant storage volumes on various version of Android (issue #745).
  - Mapper relies on undocumented environment variables and fixed fallback paths for locating map files.
  - Environment variable `SECONDARY_STORAGE` was removed in Android 6.0, internally using StorageVolume instead. 
    However, StorageVolume and a method to get a list of all volumes was made public only in Android 7.0.

- Mapper may be unable to write to secondary storage volumes.
  - The `WRITE_EXTERNAL_STORAGE` permission grants access to the primary volume only since Android 4.2.
  - The user may not notice the issue when working on a map before trying to save the file (or getting an auto-save error).
  - This may be the reason for problems reported by some users.

- The same volume may appear in different paths, leading to files being listed multiple times. (This is not a reported issue but was found when trying to scan more locations.)

- There is no problem (yet, Android 6.0) with finding and accessing (`WRITE_EXTERNAL_STORAGE`) the primary storage. However, the environment variable `EXTERNAL_STORAGE` is undocumented, in contrast to the API method [`Environment.getExternalStorageDirectory`](https://developer.android.com/reference/android/os/Environment.html#getExternalStorageDirectory()) and the `/sdcard` path (which is used by Mapper as a fallback, at least).

## Possible Changes

### Primary external storage

- The primary external storage can be determined through documented API, instead of relying on undocumented details.
- Information about the type of external storage could be given to the user (emulated = builtin storage, otherwise: memory card (?))

### Secondary external storage

- Scanning more native paths (such as all subdirs of `/storage` and `mnt`) results in multiple listing of files. OTOH the result might remain incomplete. :-1:

- Using the volumes provided by [`QStorageInfo::mountedVolumes`](http://doc.qt.io/qt-5/qstorageinfo.html#mountedVolumes) turned out to be likewise incomplete and inconsistent across devices. The implementation parses `/proc/mounts` which may give quite different result over various devices and versions. :-1: 

- Syntesized Permissions exists since Android 4.4 at least and requires no extra effort for write access to particular directories. However, these folders are deleted when the app is removed. :-1:

  However, [`Context.getExternalFilesDirs`](https://developer.android.com/reference/android/content/Context.html#getExternalFilesDirs(java.lang.String)) could be the best tool to determine all storage volumes.

- Native write access to arbitrary folders on secondary storage volumes will be possible only after getting permission through Android 7.0 Java APIs (Scoped Directory Access). This excludes nearly all current devices. :-1: 

- The Storage Access Framework gives access to a broad range of providers through Android 4.4 Java API. This might be powerful but is quite complex for a native app such as Mapper. :sleepy: 

- *The simplest thing is to declare secondary storage being no longer supported.* This is more or lese the current state: writing to these locations is not possible.

  To mitigate the impact of background images on the capacity of the primary storage (especially when emulated), secondary storage could be supported as a read-only location.