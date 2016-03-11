OpenOrienteering Mapper supports localization. This page gives an overview and hints to both translators and programmers. 


## Present state

### Mapper 0.6.1 (current release)

The user interface is translated to the following languages:

  * **Čeština (Czech - cs)**: incomplete :star::star::star:
    <br/>1173 translations (1167 finished and 8 unfinished), 66 untranslated source texts
  * **Deutsch (German - de)**: complete :star::star::star::star::star:
    <br/>1239 translations (1239 finished and 0 unfinished)
    <br/>@dg0yt
  * **English (en)**: nearly complete (plural forms only) :star::star::star::star::star:
    <br/>4 translations (4 finished and 0 unfinished)
    <br/>@dg0yt
  * **Español de España (Spanish - es)**: incomplete :star::star::star:
    <br/>1172 translations (1167 finished and 7 unfinished), 67 untranslated source texts
  * **Suomi (Finnish - fi)**: incomplete :star::star::star:
    <br/>1056 translations (1018 finished and 38 unfinished), 183 untranslated source texts 
  * **Français (French - fr)**: incomplete :star::star:
    <br/>979 translations (938 finished and 41 unfinished), 260 untranslated source texts 
  * **Magyar (Hungarian - hu)**: incomplete :star::star::star:
    <br/>1192 translations (1159 finished and 33 unfinished), 47 untranslated source texts 
  * **Italiano (Italian - it)**: incomplete :star::star::star:
    <br/>1199 translations (1193 finished and 6 unfinished), 40 untranslated source texts 
  * **日本語 (Japanese - ja)**: incomplete :star::star:
    <br/>922 translations (880 finished and 6 unfinished), 317 untranslated source texts
  * **Latviešu (Latvian - lv)**: incomplete :star::star:
    <br/>980 translations (938 finished and 42 unfinished), 259 untranslated source texts
  * **Norsk bokmål (Norwegian Bokmål - nb)**: nearly complete :star::star::star::star:
    <br/>1236 translation(s) (1233 finished and 3 unfinished), 3 untranslated source texts
    <br/>@cschive
  * **Polski (Polish - pl)**: incomplete :star::star:
    <br/>968 translations (908 finished and 60 unfinished), 271 untranslated source texts
  * **Русский (Russian - ru)**: nearly complete :star::star::star::star:
    <br/>1237 translations (1235 finished and 2 unfinished), 2 untranslated source texts
    <br/>@sembruk
  * **Svenska (Swedish - sv)**: nearly complete :star::star::star::star:
    <br/>1235 translations (1232 finished and 3 unfinished), 4 untranslated source texts
    <br/>@Abbe98
  * **Українська мова (Ukrainian - uk)**: nearly complete :star::star::star::star:
    <br/>1234 translations (771 finished and 463 unfinished), 5 untranslated source texts
    <br/>@yevhenmazur

### Next release (Mapper 0.6.2)

The user interface is translated to the following languages:

  * **Čeština (Czech - cs)**: nearly complete :star::star::star::star:
    <br/>1237 translations (1235 finished and 2 unfinished), 9 untranslated source texts
  * **Deutsch (German - de)**: nearly complete :star::star::star::star:
    <br/>1237 translations (1235 finished and 2 unfinished), 9 untranslated source texts
    <br/>@dg0yt
  * **English (en)**: complete (plural forms only) :star::star::star::star::star:
    <br/>2 translations (2 finished and 0 unfinished)
    <br/>@dg0yt
  * **Español de España (Spanish - es)**: incomplete :star::star::star:
    <br/>1170 translations (1162 finished and 8 unfinished), 76 untranslated source texts
  * **Suomi (Finnish - fi)**: incomplete :star::star::star:
    <br/>1055 translations (1016 finished and 39 unfinished), 191 untranslated source texts 
  * **Français (French - fr)**: nearly complete :star::star::star::star:
    <br/>1237 translations (1235 finished and 2 unfinished), 9 untranslated source texts 
  * **Magyar (Hungarian - hu)**: incomplete :star::star::star:
    <br/>1190 translations (1156 finished and 34 unfinished), 56 untranslated source texts 
  * **Italiano (Italian - it)**: incomplete :star::star::star:
    <br/>1197 translations (1190 finished and 7 unfinished), 49 untranslated source texts 
  * **日本語 (Japanese - ja)**: incomplete :star::star:
    <br/>922 translations (879 finished and 43 unfinished), 324 untranslated source texts
  * **Latviešu (Latvian - lv)**: incomplete :star::star:
    <br/>980 translations (937 finished and 43 unfinished), 266 untranslated source texts
  * **Norsk bokmål (Norwegian Bokmål - nb)**: nearly complete :star::star::star::star:
    <br/>1236 translation(s) (1235 finished and 1 unfinished), 10 untranslated source text
    <br/>@cschive, @kjetilk
  * **Polski (Polish - pl)**: incomplete :star::star:
    <br/>968 translations (907 finished and 61 unfinished), 278 untranslated source texts
  * **Русский (Russian - ru)**: nearly complete :star::star::star::star:
    <br/>1236 translations (1235 finished and 1 unfinished), 10 untranslated source texts
    <br/>@sembruk
  * **Svenska (Swedish - sv)**: nearly complete :star::star::star::star:
    <br/>1233 translations (1229 finished and 4 unfinished), 13 untranslated source texts
    <br/>@Abbe98
  * **Українська мова (Ukrainian - uk)**: nearly complete :star::star::star::star:
    <br/>1237 translations (1235 finished and 2 unfinished), 9 untranslated source texts
    <br/>@yevhenmazur


## Information for Translators

Translation efforts should first focus on standard user interface items such as menu entries, window titles, button labels etc. 

Translation is done with [Qt Linguist](http://doc.qt.io/qt-5/linguist-translators.html). It can be installed as selectable component in the [Qt SDK installer](http://www.qt.io/download-open-source/), but we provide a [stand-alone download](https://sourceforge.net/projects/oorienteering/files/Mapper/0.5.96/translations/). For every supported language, there is a .ts-file in the [translations directory](https://github.com/OpenOrienteering/mapper/tree/master/translations/), which contains both the strings to be translated and the actual translations. 

At the moment, there are app. 1250 translatable strings. 

### New Languages

To start the translation for a new language, you can start with the [template .ts-file](https://raw.githubusercontent.com/OpenOrienteering/mapper/master/translations/OpenOrienteering_template.ts). You can submit the new translation with a pull request or an issue on [Github](https://github.com/OpenOrienteering/mapper/). 

### Updating Translations

To update or modify an existing translation you can download the latest version from the [translations directory](https://github.com/OpenOrienteering/mapper/tree/master/translations/) or use git to checkout the source code including the translations directory: 

      git clone https://github.com/OpenOrienteering/mapper.git

You can submit the updated translation with a pull request or an issue on [Github](https://github.com/OpenOrienteering/mapper/). 

When the developers add new strings to the source code, these strings have to be added to the the .ts-files. This is done by calling the lupdate program with the proper sources and targets. For platforms where /bin/sh is available a script translations/update-translations.sh is provided which automates that process. 

**Warning:** Since the .ts-file contains the translated strings, you might loose translations which are not yet in the git repository when you download a fresh copy of the file from the git repository. Make a backup of your work if you are in doubt. For merging translations see below. 

### Testing Translations

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
