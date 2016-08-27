# Difference between mobile platform and desktop version

* Screen size
* Screen resolution
* Touch control instead of mouse + keyboard
* Non-traditional file storage

# File storage

## External Storage on Android

*Cf. https://source.android.com/devices/storage/*

Although called "external", this storage may include emulated storage which actually resides on internal storage.

- Traditional storage
  - Portable storage: a physical media, such as an SD card (since Android 1.0) or USB device (since Android 6.0)
  - Emulated storage: a portion of the internal (unremovable) storage, exposed through an emulation layer (since Android 3.0)
- Adoptable storage (since Android 6.0):
  provided by physical media, like an SD card or USB, but encrypted and formatted to behave like internal storage, and thus tied to a particular device.

## How Mapper looks from maps

Given the `WRITE_EXTERNAL_STORAGE` permission, Mapper is able read from to write to some locations which used to cover the internal memory and memory cards (SD cards). Mapper looks for a folder named `OOMapper` in the following locations:
- the location given in the environment variable `EXTERNAL_STORAGE`
- all locations given in the environment variable `SECONDARY_STORAGE` (separated by `:`)

If this folder was not found in the previous locations, it continues with the following ones (serving as a fallback):
- `/`
- `/mnt`
- `/mnt/sdcard`
- `/sdcard`
- `/storage`

