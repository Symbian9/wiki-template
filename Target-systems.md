# Notes on target systems

## Windows and Linux packages on OBS

We provide Mapper releases for Windows and a number of Linux distributions on openSUSE Build Service (OBS). The build [openorienteering-mapper-unstable in home:dg0yt:staging](https://build.opensuse.org/package/show/home:dg0yt:staging/openorienteering-mapper-unstable) is triggered by each push to the mapper repository on GitHub. Successful builds need to be explicitly released to the home:dg0yt project by calling

```
osc release home:dg0yt:staging openorienteering-mapper-unstable
```

The released downloads are available here:
- Windows: http://download.opensuse.org/repositories/home:/dg0yt/Windows/
- Linux:   https://software.opensuse.org/download.html?project=home%3Adg0yt&package=openorienteering-mapper-unstable


## Component Version Matrix

For unstable/upcoming release:

Target System | CMake       | C++         | Qt          | Polyclipping | Proj.4      | Remark
--------------|-------------|-------------|-------------|--------------|-------------|-------------
Android       |             | gcc 4.8 :-1: | 5.5.1       | 6.1.3a       | 4.9.2 :+1:  | local build
Arch          | 3.3.2       | gcc 5.2.0   | 5.5.1       | 6.1.3a       | 4.9.1 :+1:  | OBS
Debian 8.0    | 3.0.2       | gcc 4.9.2   | 5.3.2       | 6.1.3a       | 4.8.0       | OBS
Fedora 21     | 3.0.2       | gcc 4.9.2   | 5.3.2       | 6.1.3a       | 4.8.0       | OBS
Fedora 22     | 3.2.2       | gcc 5.1.1   | 5.4.1       | 6.1.3a       | 4.8.0       | OBS
openSUSE 13.2 | 3.0.2       | gcc 4.8.3 :-1: | 5.3.2       | 6.1.3a       | 4.8.0       | OBS
openSUSE Tumbleweed | 3.3.2 | gcc 5.1.1   | 5.5.0       | 6.1.3a       | 4.9.2 :+1:  | OBS
OS X          |             | XCode 7.0   | 5.5.1       | 6.1.3a       | 4.9.2 :+1:  | local build
Ubuntu 14.04  | 2.8.12 :-1: | gcc 4.8.2 :-1: | 5.2.1 :-1:  | 6.1.3a       | 4.8.0       | OBS
Ubuntu 15.04  | 3.0.2       | gcc 4.9.2   | 5.4.1       | 6.1.3a       | 4.8.0       | OBS
Ubuntu 15.10  | 3.2.2       | gcc 5.2.1   | 5.4.2       | 6.1.3a       | 4.9.1 :+1:  | OBS
Windows       | 3.0.2       | gcc 5.2.0   | 5.5.1       | 6.1.3a       | 4.9.2 :+1:  | OBS/openSUSE 13.2

* Qt < 5.3 needs extra treatment in some places.
* gcc < 4.9 does not have C++14 std::make_unique_ptr.

## Arch Linux

- [Arch Linux package database](https://www.archlinux.org/packages/)
- [Arch User Repository (AUR)](https://aur.archlinux.org/packages/)
  - [Mapper in AUR](https://aur.archlinux.org/packages/?K=openorienteering) (3rd-party)


## Fedora

- [Fedora buildsystem (Koji)](http://koji.fedoraproject.org/koji/index)
- [Fedora packages](https://apps.fedoraproject.org/packages/)

