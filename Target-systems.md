# Notes on target systems

 * [Windows and Linux packages on OBS](#windows-and-linux-unstable-packages-on-obs)
 * [Packages in Linux distributions](#packages-in-linux-distributions)
 * [Component version matrix](#component-version-matrix)

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



## Packages in Linux Distributions

[![Packaging status](https://repology.org/badge/vertical-allrepos/openorienteering-mapper.svg)](https://repology.org/metapackage/openorienteering-mapper)

Source: https://repology.org/metapackage/openorienteering-mapper

### Arch Linux

- [Creating packages](https://wiki.archlinux.org/index.php/Creating_packages)
- [Arch Linux package database](https://www.archlinux.org/packages/)
- [Arch User Repository (AUR)](https://aur.archlinux.org/packages/)
  - [Mapper in AUR](https://aur.archlinux.org/packages/openorienteering-mapper/) <br />
    ![](https://img.shields.io/aur/version/openorienteering-mapper.svg)
    ![](https://img.shields.io/aur/votes/openorienteering-mapper.svg)
  - [Mapper (git) in AUR](https://aur.archlinux.org/packages/openorienteering-mapper-git/) <br />
    ![](https://img.shields.io/aur/version/openorienteering-mapper-git.svg)
    ![](https://img.shields.io/aur/votes/openorienteering-mapper-git.svg)


### Debian

- [Debian Packages](https://www.debian.org/distrib/packages)
  - [Mapper in Debian Package Tracker](https://tracker.debian.org/pkg/openorienteering-mapper)
  - [Mapper screenshots page](https://screenshots.debian.net/package/openorienteering-mapper)
  - [Lintian report](https://lintian.debian.org/full/gaudenz@debian.org.html#openorienteering-mapper)
  - Popularity (popcon):

    ![openorienteering-mapper popcon graph](https://qa.debian.org/cgi-bin/popcon-png?packages=openorienteering-mapper&show_installed=on&want_legend=on&want_ticks=on&date_fmt=%25Y-%25m&beenhere=1)


### Fedora

- [Fedora RPM Guide](https://docs.fedoraproject.org/en-US/Fedora_Draft_Documentation/0.1/html/RPM_Guide/)
- [Fedora buildsystem (Koji)](http://koji.fedoraproject.org/koji/index)
- [Fedora packages](https://apps.fedoraproject.org/packages/)


### Ubuntu

- [Ubuntu Packages](http://packages.ubuntu.com/)
  - [Mapper in Launchpad](https://launchpad.net/ubuntu/+source/openorienteering-mapper)
  - [Mapper screenshots page](https://screenshots.debian.net/package/openorienteering-mapper)

### Slackware

- [Mapper for Slackware 14.2 on SlackBuilds.org](https://slackbuilds.org/repository/14.2/gis/openorienteering-mapper/)


## Component Version Matrix

### Next Linux distribution releases

Component | Versions
----------|---------
CMake | [![Arch package](https://repology.org/badge/version-for-repo/arch/cmake.svg) ![debian_testing](https://repology.org/badge/version-for-repo/debian_testing/cmake.svg) ![fedora_rawhide](https://repology.org/badge/version-for-repo/fedora_rawhide/cmake.svg) ![opensuse_tumbleweed](https://repology.org/badge/version-for-repo/opensuse_tumbleweed/cmake.svg)](https://repology.org/metapackage/cmake)
gcc | [![Arch package](https://repology.org/badge/version-for-repo/arch/gcc.svg) ![debian_testing](https://repology.org/badge/version-for-repo/debian_testing/gcc.svg) ![fedora_rawhide](https://repology.org/badge/version-for-repo/fedora_rawhide/gcc.svg) ![opensuse_tumbleweed](https://repology.org/badge/version-for-repo/opensuse_tumbleweed/gcc.svg)](https://repology.org/metapackage/gcc)
GDAL | [![Arch package](https://repology.org/badge/version-for-repo/arch/gdal.svg) ![debian_testing](https://repology.org/badge/version-for-repo/debian_testing/gdal.svg) ![fedora_rawhide](https://repology.org/badge/version-for-repo/fedora_rawhide/gdal.svg) ![opensuse_tumbleweed](https://repology.org/badge/version-for-repo/opensuse_tumbleweed/gdal.svg)](https://repology.org/metapackage/gdal)
polyclipping | [![](https://img.shields.io/badge/Arch_package-n.a.-red.svg) ![debian_testing](https://repology.org/badge/version-for-repo/debian_testing/polyclipping.svg) ![fedora_rawhide](https://repology.org/badge/version-for-repo/fedora_rawhide/polyclipping.svg) ![](https://img.shields.io/badge/openSUSE_Tumbleed_package-n.a.-red.svg)](https://repology.org/metapackage/polyclipping)
PROJ.4 | [![Arch package](https://repology.org/badge/version-for-repo/arch/proj.svg) ![debian_testing](https://repology.org/badge/version-for-repo/debian_testing/proj.svg) ![fedora_rawhide](https://repology.org/badge/version-for-repo/fedora_rawhide/proj.svg) ![opensuse_tumbleweed](https://repology.org/badge/version-for-repo/opensuse_tumbleweed/proj.svg)](https://repology.org/metapackage/proj)
Qt | [![Arch package](https://repology.org/badge/version-for-repo/arch/qt5-qtbase.svg) ![debian_testing](https://repology.org/badge/version-for-repo/debian_testing/qt5-qtbase.svg) ![fedora_rawhide](https://repology.org/badge/version-for-repo/fedora_rawhide/qt5-qtbase.svg) ![opensuse_tumbleweed](https://repology.org/badge/version-for-repo/opensuse_tumbleweed/qt5-qtbase.svg)](https://repology.org/metapackage/qt5-qtbase)

Source: https://repology.org


### Unstable and 0.7.x releases

Target System | CMake | C++         | Qt          | Poly- clipping | Proj.4      |  GDAL       | Remark
--------------|-------------|-------------|-------------|----------------|-------------|-------------|-------------
[Android](Android)        | 3.7    | gcc 4.9    | 5.6.2  | 6.1.3a | 4.9.2  | 2.1.2  | local superbuild
[Arch Linux](#arch-linux) | 3.8.2  | gcc 7.1.1  | 5.9.0  | 6.4.2 | 4.9.3  | 2.1.2  | OBS, [AUR](#arch-linux)
Debian 8.0                | 3.0.2 :-1: | gcc 4.9.2  | 5.3.2  | 6.1.3a | 4.8.0  | 1.10.1 :-1: | OBS
Debian 9.0                | 3.7.1  | gcc 6.3.0  | 5.7.1  | 6.1.3a | 4.9.3  | 2.1.2  | OBS, [Debian](#debian)
[Debian](#debian) testing | 3.7.1  | gcc 6.3.0  | 5.7.1  | 6.1.3a | 4.9.3  | 2.1.2  | OBS, [Debian](#debian)
Fedora 23                 | 3.3.2  | gcc 5.1.1  | 5.5.0  | 6.1.3a | 4.9.1  | 2.0.1  | OBS
[Fedora](#fedora) 24      | 3.5.2  | gcc 6.1.1  | 5.6.0  | 6.1.3a | 4.9.2  | 2.0.2  | OBS
[Fedora](#fedora) 25      | 3.6.2  | gcc 6.2.1  | 5.7.0  | 6.1.3a | 4.9.2  | 2.1.0  | OBS
Linux Mint 18.x (= Ubuntu 16.04) | 3.2.2  | gcc 5.2.1  | 5.5.1  | 6.1.3a | 4.9.2  | 1.11.3 :-1: | no build
macOS (aka OS X)          | 3.x    | XCode 7.0  | 5.5.1  | 6.1.3a | 4.9.2  | -.-.-  | local build
openSUSE Leap 42.1        | 3.3.2  | gcc 5.2.1  | 5.5.0  | 6.1.3a | 4.9.2  | 1.11.3 :-1: | OBS
openSUSE Leap 42.2        | 3.5.2  | gcc 5.3.1  | 5.6.1  | 6.1.3a | 4.9.2  | 2.1.0  | OBS
openSUSE Tumbleweed       | 3.7.1  | gcc 6.2.1  | 5.7.1  | 6.1.3a | 4.9.3  | 2.1.2  | OBS
[Slackware](#slackware) 14.2 | 3.5.2 | gcc 5.3.0 | Qt 5.7.1 (SBo) | 6.4.2 (SBo) | 4.9.3 (SBo) | 2.2.0 (SBo) | [SlackBuilds.org](#slackware)
[Ubuntu](#ubuntu) 16.04   | 3.5.1  | gcc 5.4.0, gcc 5.3.1  | 5.5.1  | 6.1.3a | 4.9.2  | 1.11.3 :-1: | OBS
[Ubuntu](#ubuntu) 16.10   | 3.5.2  | gcc 6.2.0  | 5.6.1  | 6.1.3a | 4.9.2  | 2.1.1  | OBS, [Launchpad](#ubuntu)
Windows                   | 3.7.1  | gcc 5.3.1  | 5.6.2  | 6.1.3a | 4.9.2  | 2.1.2  | OBS/openSUSE Leap 42.2/superbuild

* CMake < 3.1 does not support ```CMAKE_CXX_STANDARD```.
* CMake < 3.2 does not support ```BYPRODUCTS``` in ```ADD_CUSTOM_TARGET```. Solved by patch.
* More providers, packages, versions: https://repology.org/

### Limited to 0.6.x releases

Target System | CMake       | C++         | Qt          | Poly- clipping | Proj.4      |  GDAL       | Remark
--------------|-------------|-------------|-------------|----------------|-------------|-------------|-------------
Linux Mint 17.x (= Ubuntu 14.04) :-1: | 2.8.12 :-1: | gcc 4.8.2 :-1: | 5.2.1 :-1: | 6.1.3a | 4.8.0  | 1.10.1 :-1: | no build
openSUSE 13.2 :-1: | 3.0.2 :-1: | gcc 4.8.3 :-1: | 5.3.2  | 6.1.3a | 4.8.0  | -.-.-  | OBS
Ubuntu 14.04 :-1: | 2.8.12 :-1: | gcc 4.8.2 :-1: | 5.2.1 :-1: | 6.1.3a | 4.8.0  | 1.10.1 :-1: | OBS

* gcc < 4.9 does not provide C++14 ```std::make_unique```.
* gcc 4.8 strictly implements a "bug in the standard" which forces the creation of temporaries when using uniform initialization in member initialization and thus leading to crashes when accessing these temporaries later (cf. http://stackoverflow.com/questions/25561387/spurious-warning-about-binding-temporary-to-reference-member-in-constructor), observed for [ReplaceSymbolSetOperation constructor](https://github.com/OpenOrienteering/mapper/blob/master/src/gui/symbols/replace_symbol_set_dialog.cpp#L51).
* Qt < 5.3 needs extra treatment in some places.
* CMake < 3.0 needs a ```windres``` workaround in ```src/CMakeLists.txt``` when locally cross-compiling for windows.
* CMake < 3.1 does not support ```CMAKE_CXX_STANDARD```.
* CMake < 3.2 does not support ```BYPRODUCTS``` in ```ADD_CUSTOM_TARGET```.
* The Android APKs are built with qmake in Qt Creator, but CMake is used to build dependencies.


