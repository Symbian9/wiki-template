Qt5 is now the default for building Qt as part of Mapper superbuilds, including release builds and packaging. 

[Introducing Qt 5](http://qt-project.org/qt5)

For build Qt5 on Linux (X11), please pay attention to the xcb build-time dependencies: http://qt.gitorious.org/qt/qtbase/blobs/HEAD/src/plugins/platforms/xcb/README 


## Qt5 Releases

### Timeline

Qt 5.0.0 was released on December 19, 2012. 

  * [Digia's Qt blog entry](http://blog.qt.digia.com/blog/2012/12/19/qt-5-0/)
  * [Qt 5.0.0 known issues](http://qt-project.org/wiki/Qt500KnownIssues)

Qt 5.0.1 was released on Januar 31, 2013 

  * [Digia's Qt blog entry](http://blog.qt.digia.com/blog/2013/01/31/qt-5-0-1-released/)
  * [Qt 5.0.1 known issues](http://qt-project.org/wiki/Qt501KnownIssues)

Qt 5.0.2 was released on April 10, 2013 

  * [Digia's Qt blog entry](http://blog.qt.digia.com/blog/2013/04/10/qt-5-0-2-released/)
  * [Qt 5.0.2 list of solved issues](https://bugreports.qt-project.org/browse/QTBUG/fixforversion/12607)
  * [Qt 5.0.2 known issues](http://qt-project.org/wiki/Qt502KnownIssues)

### Changes and porting from Qt 4 to Qt 5

  * [Changes](http://qt.gitorious.org/qt/qtbase/blobs/master/dist/changes-5.0.0)
  * [Transition from Qt 4.x to Qt 5](http://qt-project.org/wiki/Transition_from_Qt_4.x_to_Qt5) in Qt Project's wiki 
  * [Porting from Qt 4 to Qt 5](http://www.kdab.com/porting-from-qt-4-to-qt-5/) by KDAB 
  * [Porting Guide](http://qt-project.org/doc/qt-5.0/qtdoc/portingguide.html) in the Qt 5.0 documentation 
  * [C++ API Changes](http://qt-project.org/doc/qt-5.0/qtdoc/sourcebreaks.html) in the Qt 5.0 documentation 

### CMake with Qt5

  * [Qt5 CMake manual](http://doc-snapshot.qt-project.org/5.0/cmake-manual.html)
  * [Using CMake with Qt 5](http://www.kdab.com/using-cmake-with-qt-5/) by KDAB 

## Building OpenOrienteering Mapper with Qt5

[Ticket:99](https://sourceforge.net/p/oorienteering/tickets/99/)

### Source code

To maintain compatibility with both Qt5 and Qt4, follow these rules: 

  * In #include, use the component name without any directory, such as 
    
       #include &lt;QWidget&gt;
    

There is one exception: 
    
       #include &lt;QtTest/QtTest&gt;
    

  * Only when neccessary, use conditional compilation depending on Qt version. A common case is including Qt4's QtGui, in Qt5 replaced by QtWidgets: 
    
       #if QT_VERSION &lt;QtGui&gt;
       #else
       #include &lt;QtWidgets&gt;
       #endif
    

  * Do no longer use the Q_WS_... macros. They are no longer defined in Qt5 (although there are still lots of #if defined(Q_WS_...) in Qt 5.0.0). Use the Q_OS_... macros for guarding operating system specific code. Cf. http://qt-project.org/doc/qt-5.0/qtcore/qtglobal.html. 
    * Q_OS_WIN for all flavors of Windows (not documented) 
    * Q_OS_MAC for Mac OS 
    * Use #if&nbsp;!defined(Q_OS_WIN) &amp;&amp;&nbsp;!defined(Q_OS_MAC) to cover most system which are neither Windows nor Mac OS. 

### CMake

Qt 5 comes with distinct CMake modules for each component of Qt5. The minimum CMake version required to use these modules is 2.8.3, but 2.8.9 is recommended. (Mapper currently supports CMake starting from 2.8.0 for Qt4 builds.) Required CMake options 

  * for downloading and building Qt 5 as part of the Mapper build process (aka superbuild; this is the default): 
    
       -DMapper_BUILD_QT=1
    

  * for using a precompiled SDK: 
    
       -DMapper_USE_QT5=1
       -DCMAKE_PREFIX_PATH=/path-to-qt5-dir
    

The build is successfully tested on Linux (gcc), on OS X (clang), on Windows (mingw-w64 gcc from mingw-builds), and for cross-compiling from Linux to Windows (mingw-w64 gcc from Ubuntu). 
