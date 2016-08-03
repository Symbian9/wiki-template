# Notes on target systems

## Windows and Linux (unstable) packages on OBS

We provide Mapper releases for Windows and a number of Linux distributions on openSUSE Build Service (OBS). The build [openorienteering-mapper-unstable in home:dg0yt:staging](https://build.opensuse.org/package/show/home:dg0yt:staging/openorienteering-mapper-unstable) is triggered by each push to the mapper repository on GitHub. Successful builds need to be explicitly released to the home:dg0yt project by calling

```
osc release home:dg0yt:staging openorienteering-mapper-unstable
```

The released downloads are available here:
- Windows: http://download.opensuse.org/repositories/home:/dg0yt/Windows/ <br />
  ![](https://img.shields.io/website-up-down-green-red/http/download.opensuse.org.svg)
- Linux:   https://software.opensuse.org/download.html?project=home%3Adg0yt&package=openorienteering-mapper-unstable <br />
  ![](https://img.shields.io/website-up-down-green-red/https/software.opensuse.org.svg)


## Component Version Matrix

For unstable/upcoming release:

Target System | CMake       | C++         | Qt          | Polyclipping | Proj.4      |  GDAL       | Remark
--------------|-------------|-------------|-------------|--------------|-------------|-------------|-------------
Android       | 3.x         | gcc 4.9     | 5.5.1       | 6.1.3a       | 4.9.2       |  . .        | local build
Arch          | 3.3.2       | gcc 5.2.0   | 5.5.1       | 6.1.3a       | 4.9.1       |  . .        | OBS
Debian 8.0    | 3.0.2       | gcc 4.9.2   | 5.3.2       | 6.1.3a       | 4.8.0 :-1:  | 1.10.1      | OBS
Fedora 22     | 3.2.2       | gcc 5.1.1   | 5.4.1       | 6.1.3a       | 4.8.0 :-1:  | 1.11.3      | OBS
Fedora 23     | 3.3.2       | gcc 5.1.1   | 5.5.0       | 6.1.3a       | 4.9.1       | 2.0.1       | OBS
Fedora 24     | 3.5.2       | gcc 6.1.1   | 5.6.0       | 6.1.3a       | 4.9.2       | 2.0.2       | OBS
Linux Mint 17.x (= Ubuntu 14.04) :-1: | 2.8.12 :-1: | gcc 4.8.2 :-1: | 5.2.1 :-1:  | 6.1.3a    | 4.8.0       | 1.10.1      | no build
Linux Mint 18.x (= Ubuntu 16.04) | 3.2.2      | gcc 5.2.1   | 5.5.1       | 6.1.3a       | 4.9.2 :+1:  | 1.11.3      | no build
macOS (aka OS X) | 3.x      | XCode 7.0   | 5.5.1       | 6.1.3a       | 4.9.2       |  . .        | local build
openSUSE 13.2 | 3.0.2       | gcc 4.8.3 :-1: | 5.3.2    | 6.1.3a       | 4.8.0 :-1:  |  . .        | OBS
openSUSE Leap 42.1  | 3.3.2 | gcc 4.8.5 :-1:, gcc 5.2.1 | 5.5.0    | 6.1.3a       | 4.9.2 :+1:  | 1.11.3      | OBS
openSUSE Tumbleweed | 3.3.2 | gcc 5.1.1, gcc 5.2.1   | 5.5.0       | 6.1.3a       | 4.9.2 :+1:  | 1.11.3      | OBS
Ubuntu 14.04 :-1: | 2.8.12 :-1: | gcc 4.8.2 :-1: | 5.2.1 :-1:  | 6.1.3a    | 4.8.0 :-1:  | 1.10.1 :-1: | OBS
Ubuntu 15.10  | 3.2.2       | gcc 5.2.1   | 5.4.2       | 6.1.3a       | 4.9.1       | 1.11.2 :-1: | OBS
Ubuntu 16.04  | 3.5.1       | gcc 5.3.1   | 5.5.1       | 6.1.3a       | 4.9.2       | 1.11.3 :-1: | OBS
Windows       | 3.0.2       | gcc 5.3.1   | 5.5.1       | 6.1.3a       | 4.9.2       |  . .        | OBS/openSUSE 13.2

* Qt < 5.3 needs extra treatment in some places.
* gcc < 4.9 does not have C++14 ```std::make_unique```.
* CMake < 3.0 needs a ```windres``` workaround in ```src/CMakeLists.txt``` when locally cross-compiling for windows.
* The Android APKs are built with qmake in Qt creator, but CMake is used to build dependencies.

## Arch Linux

- [Arch Linux package database](https://www.archlinux.org/packages/)
- [Arch User Repository (AUR)](https://aur.archlinux.org/packages/)
  - [Mapper in AUR](https://aur.archlinux.org/packages/?K=openorienteering) <br />
    ![](https://img.shields.io/aur/version/openorienteering-mapper.svg)
    ![](https://img.shields.io/aur/votes/openorienteering-mapper.svg)


## Fedora

- [Fedora buildsystem (Koji)](http://koji.fedoraproject.org/koji/index)
- [Fedora packages](https://apps.fedoraproject.org/packages/)

