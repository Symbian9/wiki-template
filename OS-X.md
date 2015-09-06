
## Building Mapper on OS X

Verified 2013-02-28. 

Ticket: https://sourceforge.net/p/oorienteering/tickets/96/ 

### Build Prerequisites

You will need to know how to use the command line ("Terminal"), and you will need an Apple Developer ID in order to download the required Apple software. 

You will need the following software: 

  * 64-bit Apple Mac OS X Lion (10.7. 10.6 and later version may work, too.) 
  * Command Line Tools for Xcode - November 2012 (from Apple, tested with the package for OS X Lion). The January 2013 package is not able to compile to Qt 5.0.0/5.0.1, due to a Qt bug. 
  * Git from http://git-scm.com/download/mac 
  * CMake 2.8.x from http://www.cmake.org/cmake/resources/software.html 
  * Optionally: Xcode (from Apple) for a full IDE (tested with 4.5.2). 4.6 will probably not be able to compile Qt 5.0.0/5.0.1. 

Other prerequisites such as Clipper library, Proj.4 library and Qt 5 SDK will be downloaded during the build. 

### Preparing the working directory

  * Open a Terminal. 
  * cd to the directory which will host your working directory. 
  * Checkout the source code with git: 
    
       git clone git://git.code.sf.net/p/oorienteering/code oorienteering-code
    

  * Change to the working directory: 
    
       cd oorienteering-code
    

You are now ready either to create an Xcode project or to configure a command-line build. 

### Command-line build project

  * From the working directory, prepare and configure a build directory: 
    
       mkdir build
       cd build
       cmake ..
    

  * From the build directory, you may now do a build by running 
    
       make
    

  * The first build may take very long, since it will download and build 3rd-party components. Qt5 (&gt;200 MB) is the biggest part. 

This shall produce a Mapper executable in src/Mapper.app/Contents/MacOS/. 

### Creating an Xcode project

  * From the working directory, prepare and configure a build directory: 
    
       mkdir build-xcode
       cd build-xcode
       cmake .. -G Xcode
    

  * Open the project in Xcode. 
  * Start a build. The first build may take very long, since it will download and build 3rd-party components. Qt5 (&gt;200 MB) is the biggest part. 
  * Remember that the primary build system is cmake. If you add files, it has to be done in the appropriate CMakeLists.txt files. There are more feature in Xcode which are not used by our project. 

### Report Your Build Problems

Report your problems on the mailing list. Include the output of the build process from the terminal, or send it to a personal e-mail address when asked. 

  


## Building Distributable Packages

You may generate a DMG which should include everything which is required to run Mapper on another compatible OS X machine. 

  * From the build directory, run: 
    
       make package
    

## Building Official Release Packages

Distributing binary code under open source licenses creates certain legal obligations, such as the distribution of the source code. This is how to do this correctly for Mapper on Systems without distributor-supplied Qt and PROJ.4, such as Mac OS X and Windows. 

Official release packages need to be build from an official source code archive. This is to make sure that every user can indeed get all required files for the release. Official release packages will include the Qt libraries and the Qt assistant executable. 

The build shall start from a fresh build directory. The build shall be in release mode. 
    
      tar xvzf openorienteering-mapper_X.Y.Z-src.tgz
      cd openorienteering-mapper_X.Y.Z
      mkdir build
      cd build
      cmake .. -DCMAKE_BUILD_TYPE=Release \
      make
      make package
    

## Finding more Qt SDK tools

All Qt tools are located in the build directory's 3rd-party/qt5/Qt5-Prefix subdirectory. You might be interested in the linguist... 

## Weblinks
    
    * Mac OS X porting (with focus on GIS software): http://www.kyngchaos.com/macosx/index (William Kyngesburye)
    
