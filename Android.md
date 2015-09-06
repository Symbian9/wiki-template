On this page information regarding Mapper for Android will be collected. It will both take on Android specifically but also mobile devices more in general.

**This page needs to be reviewed. QML is _not used_ for the current Android port.**


## Differences to PC version

The two main differences to the PC version of Mapper are screen size and controlling 

### Screen size

Most of the time, the screen on a mobile device is smaller than on a computer. Because of this, the UI has to be redone. If possible, this should be done in QML, as that would allow a nice looking, fluid, UI, and even though Map-makers usually aren't end users a nice UI would still be nice. See [#QML_based_GUI] 

### Controlling

You also normally don't have a mouse or a keybord. 

This is about how it could map: 

  * Mouse wheel (zoom) -&gt; Pinching with fingers 
  * Mouse left button (selecting) -&gt; Taping with finger 
  * Mouse left button + Ctrl -&gt; Holding with finger 
  * Mouse middle button (panning) -&gt; Slide with fingers 

TODO: Add more mappings 

## QML based GUI

As outlined in [#Screen_size], a different UI is almost a must, and QML should be the prefered way to do it. The following is a small proposal for how to UI might look: 

![](files/MapperQMLGUIMockup.png) 

A and B would be toolboxes, sliding them to the left or taping them would make the part with the letters (should be icons) go as long way to the right as nessecary to show all contained tools, and if it wouldn't fit at all it should be possible to scroll in the toolbox. As soon as a tool has been selected the toolbox should retract again. C would be the same but it would be for the symbols and would slide up fart enough to display two rows of symbols, which then could be scrolled. 

This only takes horizontal mode into account, the question is if vertical mode is needed at all. 

## Devices that could run Mapper

As Mapper is written using the Qt Toolkit, it should be possible to run it on all devices running Qt (including, but not limited to computers, tablets, smartphones and coffe machines). 

Mostly, releases for them depends on when Digia releases an official Qt port for the device 

### Platforms with porting priority 1

  * Android (smartphones and tablets) (Qt port supposed to come with 5.2 in late summer, early autumn) 
  * BB10 (smartphones and tablets) (Qt port available) 

#### Android

http://blog.qt.digia.com/blog/2013/03/13/preview-of-qt-5-for-android/ 

### Platforms with porting priority 2

  * Raspberry PI (credit card sized computer, more because of doing it than any use) (Qt port available) 
  * iOS (smartphones and tablets, might need special licenses, paying fees etc) (Qt port supposed to come with 5.2 in late summer, early autumn) 

## What needs to be done

First everything (except maybe touch) should be working on a computer, that would firstly speed up development (not needing to deploy all the time), and as Qt is cross-platform, it should then work on Android etc. with only minor tweaks. 

The first step would be to isolate all code that in some way depends on QWidget (QMainWindow etc.) from the codebase, preferably by creating interfaces or abstract classes with (for the beginning) a QWidget class child. That way it would later be easy to create a QML/QtQuick child instead. 

Once that is done to all classes, several QtQuick items need to be created. For the first, one for the map it self, secondly one for the symbol pane (both shouldn't need to much work) and lastly one for the toolboxes. These then need to be merged in a QML file. Using those classes, it shouldn't be to hard to create the QML file, even for a non-UI designer, but it might still be nice if someone who knows how to do it in real would do it&nbsp;:) 

### The above in a numbered list

  1. Split all classes that use QWidget code into one interface/abstract class and one implementation using widget based code **IN PROGRESS**
  2. Create another implementation for each of the interfaces/abstract classes for a QML UI 
    1. Create a QML version of the map widget and the symbol pane 
  3. Create a QML file joining everything 
  4. Clean up and make sure both versions still compile 
  5. Compile for and deploy on a mobile device running Android, BB10 or similar 
  6. Create a touch based UI 
  7. Release!!! 

## Changelog (or: what has been done)

10 April 2013: First class (MapWidget) has been fully split 

12 March 2013: Created this page 

### Development

Right now, all development is done in [here](https://sourceforge.net/u/jandalheimer/oorienteering/?branch=ref%2Fqml), check it for the latest updates 
