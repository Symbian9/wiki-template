OpenOrienteering Mapper supports localization. This page gives an overview and hints to both translators and programmers. 


## Present state

### Translation issues

[All issues with label translation](https://github.com/OpenOrienteering/mapper/labels/translations)

### Next release (Mapper 0.6.4) and unstable development snapshot

The user interface is translated to the following languages:

  * Čeština (Czech - cs) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/cd/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/cs/)
  * Deutsch (German - de)
[![Translation status](https://hosted.weblate.org/widgets/openorienteering/de/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/de/)
  * English (en), plural forms only [![Translation status](https://hosted.weblate.org/widgets/openorienteering/en/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/en/)
  * Español de España (Spanish - es) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/es/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/es/)
  * Suomi (Finnish - fi) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/fi/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/fi/) 
  * Français (French - fr) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/fr/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/fr/)
  * Magyar (Hungarian - hu) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/hu/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/hu/) 
  * Italiano (Italian - it) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/it/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/it/) 
  * 日本語 (Japanese - ja) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/ja/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/ja/)
  * Latviešu (Latvian - lv) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/lv/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/lv/)
  * Norsk bokmål (Norwegian Bokmål - nb) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/nb/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/nb/)
  * Polski (Polish - pl) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/pl/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/pl/)
  * Portuguese (Brazil - pt_BR) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/pt_BR/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/pt_BR/)
  * Русский (Russian - ru) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/ru/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/ru/)
  * Svenska (Swedish - sv) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/sv/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/sv/)
  * Українська мова (Ukrainian - uk) [![Translation status](https://hosted.weblate.org/widgets/openorienteering/uk/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/uk/)


## Information for Translators

Translation efforts should first focus on standard user interface items such as menu entries, window titles, button labels etc. 

### Translation online with [Weblate](https://hosted.weblate.org/engage/openorienteering/)

<a href="https://hosted.weblate.org/engage/openorienteering/">
<img src="https://hosted.weblate.org/widgets/openorienteering/-/287x66-grey.png" alt="Translation status" />
</a>

Weblate is the most convenient way to start contributing translations. However, there is no easy way to test the translations until they eventually arrive in an unstable build.

### Translation offline with Qt Linguist

[Qt Linguist](http://doc.qt.io/qt-5/linguist-translators.html) can be installed as part of the [Qt SDK installer](http://www.qt.io/download-open-source/) or as part of Linux distributions' Qt5 development tools packages (e.g. qttools5-dev-tools). Linguist is also included in our [unstable Windows package](http://download.opensuse.org/repositories/home:/dg0yt/Windows/).

You may either use git to clone our source code repository, or download and extract a [ZIP-Archive of the master branch](https://github.com/OpenOrienteering/mapper/archive/master.zip). For every supported language, there is a .ts-file in the [translations directory](https://github.com/OpenOrienteering/mapper/tree/master/translations/), which contains both the strings to be translated and the actual translations. 

#### New Languages

To start the translation for a new language offline, you can start with the [template .ts-file](https://raw.githubusercontent.com/OpenOrienteering/mapper/master/translations/OpenOrienteering_template.ts). You can submit the new translation with a pull request or an issue on [Github](https://github.com/OpenOrienteering/mapper/). 

#### Updating Translations

To update or modify an existing translation you can download the latest version from the [translations directory](https://github.com/OpenOrienteering/mapper/tree/master/translations/) or use git to checkout the source code including the translations directory: 

      git clone https://github.com/OpenOrienteering/mapper.git

You can submit the updated translation with a pull request or an issue on [Github](https://github.com/OpenOrienteering/mapper/). 

When the developers add new strings to the source code, these strings have to be added to the the .ts-files. This is done by calling the lupdate program with the proper sources and targets. For platforms where /bin/sh is available a script translations/update-translations.sh is provided which automates that process. 

**Warning:** Since the .ts-file contains the translated strings, you might loose translations which are not yet in the git repository when you download a fresh copy of the file from the git repository. Make a backup of your work if you are in doubt. For merging translations see below. 

#### Testing Translations

To test your translation, you must generate a .qm file and make it available to your Mapper program. Your can save a .qm file from Qt Linguist. Than it should be enough to put the resulting .qm file to the "translations" subdirectory of the Mapper executable directory, or to select it from the settings dialog. The file must be named OpenOrienteering_YOURLOCALE.qm (e.g. OpenOrienteering_de.qm). The desired language can be chosen in the settings dialog (menu "File" &gt; "Settings..."). 

### Translation Qt

Some strings in the user interface come from the Qt library which is used by Mapper. Examples are the standard dialog buttons (OK, Cancel, Help, etc.) which are used in many places such as the settings dialog. 

Unfortunately, the library's translation is rather incomplete at the moment. So we provide another template which can be used to provide a minimal translation of Qt. The download is here: [template .ts-file](https://github.com/OpenOrienteering/mapper/tree/master/translations/qt_template.ts?format=raw)

  


## Information for Programmers

  * Learn about the [Qt translation framework from a programmer's point of view](http://qt-project.org/doc/qt-5.0/qtlinguist/linguist-programmers.html). 
  * Add tr("....") to strings to be translated. In case of UTF-8 characters which are not part of the Latin-1 charset, use trUtf8("...") instead. 
  * For standard dialog box buttons, use [QDialogButtonBox](http://qt-project.org/doc/qt-5.0/qtwidgets/qdialogbuttonbox.html) with the appropriate [StandardButtons](http://qt-project.org/doc/qt-5.0/qtwidgets/qdialogbuttonbox.html#StandardButton-enum). This class will use the platform look and feel, and it removes the necessity to introduce translatable string for standard buttons. 
  * Keep translations in mind when constructing phrases: 
    * Find a good phrase before first commit. 
    * Don't introduce many variants of phrases when standardization is easily possible. 
  * Even units of measurement might need translation. For disambiguation, supply a second parameter to tr(), e.g. 
    
      tr("m", "meters")
    

## Maintaining Translations in the Build System

  * Translations (.ts files) shall be saved in the translations directory. 
  * Translations must be added to the Mapper_TRANS variable in CMakeLists.txt. 
  * Translations may be updated by calling "make Mapper_translations_update" (for all translations and the template), "make Mapper_OpenOrienteering_XX_update" (for language XX), or "make Mapper_OpenOrienteering_template_update" (for the template only). 

  


## Merging translations

Sometimes it may be useful to merge several translations into a single file, e.g. to provide a single download file which contains both Mapper and Qt translations. This can be achieved with the lconvert tool from the Qt SDK. This is a versatile tool which actually can convert a number of different formats. 
