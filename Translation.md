OpenOrienteering Mapper supports localization. This page gives an overview and hints to both translators and programmers. 


## Present state

For the coming release 0.6.0, the user interface is translated to the following languages (as of release 0.5.93):

  * **Čeština (Czech - cs)**: complete
    1194 translations (1194 finished and 0 unfinished), 2 untranslated source texts
  * **Deutsch (German - de)**: complete
    1192 translations (1192 finished and 0 unfinished), 2 untranslated source texts 
  * **English (en)**: complete
    (Not a translation, but the language used in the source code.)
  * **español de España (Spanish - es)**: incomplete
    1030 translations (994 finished and 36 unfinished), 201 untranslated source texts
  * **Français (French - fr)**: incomplete
    1030 translations (994 finished and 36 unfinished), 201 untranslated source texts 
  * **日本語 (Japanese - ja)**: incomplete
    971 translations (938 finished and 33 unfinished), 265 untranslated source texts
  * **Latviešu (Latvian - lv)**: incomplete
    1031 translations (994 finished and 37 unfinished), 200 untranslated source texts
  * **norsk bokmål (Norwegian Bokmål - nb)**: complete
    1241 translation(s) (1241 finished and 0 unfinished) 
  * **polski (Polish - pl)**: incomplete
    1018 translations (963 finished and 55 unfinished), 212 untranslated source texts
  * **suomi (Finnish - fi)**: incomplete
    1119 translations (1087 finished and 32 unfinished), 122 untranslated source texts
  * **svenska (Swedish - sv)**: incomplete, may be removed!
    643 translations (539 finished and 104 unfinished), 569 untranslated source texts
  * **українська мова (Ukrainian - uk)**: incomplete, may be removed!
    667 translations (542 finished and 125 unfinished), 548 untranslated source texts



In the current binary release 0.5.3, including post-release translation updates, the user interface is translated to the following languages: 

  * **Čeština (Czech - cs)**: complete (100 %) 
  * **Deutsch (German - de)**: complete (100 %) 
  * **English (en)**: not a translation, but the language used in the source code 
  * **español de España (Spanish - es)**: complete (95%) 
  * **Français (French - fr)**: complete (95%) 
  * **日本語 (Japanese - ja)**: incomplete (86%) 
  * **Latviešu (Latvian - lv)**: complete (95%) 
  * **norsk bokmål (Norwegian Bokmål - nb)**: complete (98%) 
  * **polski (Polish - pl)**: complete (92%) 
  * **svenska (Swedish - sv)**: incomplete (51%) 
  * **українська мова (Ukrainian - uk)**: incomplete (51%) 

## Information for Translators

Translation efforts should first focus on standard user interface items such as menu entries, window titles, button labels etc. 

Translation is done with [Qt Linguist](http://qt-project.org/doc/qt-5.0/qtlinguist/linguist-translators.html). It can be installed as selectable component in the [Qt SDK installer](http://qt-project.org/downloads), but we provide a stand-alone download in the translations subdirectory of the 0.5.0 release. For every supported language, there is a .ts-file in the [translations directory](https://sourceforge.net/p/oorienteering/code/ci/master/tree/translations/), which contains both the strings to be translated and the actual translations. 

At the moment, there are app. 1100 translatable strings. 

### New Languages

To start the translation for a new language, you can start with the [template .ts-file](https://sourceforge.net/p/oorienteering/code/ci/master/tree/translations/OpenOrienteering_template.ts?format=raw). You can submit the new translation in a bug report. 

### Updating Translations

To update or modify an existing translation you can download the latest version from the [translations directory](https://sourceforge.net/p/oorienteering/code/ci/master/tree/translations/) or use git to checkout the source code including the translations directory: 
    
      git clone git://git.code.sf.net/p/oorienteering/code oorienteering
    

When the developers add new strings to the source code, these strings have to be added to the the .ts-files. This is done by calling the lupdate program with the proper sources and targets. For platforms where /bin/sh is available a script translations/update-translations.sh is provided which automates that process. 

**Warning:** Since the .ts-file contains the translated strings, you might loose translations which are not yet in the git repository when you download a fresh copy of the file from the git repository. Make a backup of your work if you are in doubt. For merging translations see below. 

### Testing Translations

To test your translation, you must generate a .qm file and make it available to your Mapper program. Your can save a .qm file from Qt Linguist. Than it should be enough to put the resulting .qm file to the "translations" subdirectory of the Mapper executable directory, or to select it from the settings dialog. The file must be named OpenOrienteering_YOURLOCALE.qm (e.g. OpenOrienteering_de.qm). The desired language can be chosen in the settings dialog (menu "File" &gt; "Settings..."). 

### Translation Qt

Some strings in the user interface come from the Qt library which is used by Mapper. Examples are the standard dialog buttons (OK, Cancel, Help, etc.) which are used in many places such as the settings dialog. 

Unfortunately, the library's translation is rather incomplete at the moment. So we provide another template which can be used to provide a minimal translation of Qt. The download is here: [template .ts-file](https://sourceforge.net/p/oorienteering/code/ci/master/tree/translations/qt_template.ts?format=raw)

  


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
