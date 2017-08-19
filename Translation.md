OpenOrienteering Mapper supports localization. This page gives an overview and hints to both translators and programmers. 

 * [Information for translators](#information-for-translators)
 * [Information for programmers](#information-for-programmers)


## Present state

### Translation issues

Github: [![Open issues with label 'translations'](https://img.shields.io/github/issues/openorienteering/mapper/translations.svg)](https://github.com/OpenOrienteering/mapper/labels/translations)<br/>
[Weblate: Failing checks](https://hosted.weblate.org/checks/?project=openorienteering)<br/>
[Weblate: Source strings to check](https://hosted.weblate.org/projects/openorienteering/mapper/source/)<br/>
[Weblate: Ignored checks](https://hosted.weblate.org/checks/?project=openorienteering&ignored=true)

### Next release (Mapper 0.7.x) and unstable development snapshot

The user interface is translated to the following languages:

| Language | Code | State |
| -------- | ---- | ----- |
| Čeština (Czech) | cs | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/cd/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/cs/) |
| Dansk (Danish)  | da | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/da/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/da/) |
| Deutsch (German) | de | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/de/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/de/) |
| English (plural forms only) | en | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/en/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/en/) |
| Español de España (Spanish) | es | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/es/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/es/) |
| Eesti (Estonian) | et | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/et/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/et/) |
| Esperanto | eo | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/eo/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/eo/) |
| Français (French) | fr | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/fr/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/fr/) |
| עברית (Hebrew, right-to-left) | he | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/he/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/he/) |
| Bahasa Indonesia (Indonesian) | id | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/id/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/id/) |
| Italiano (Italian) | it | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/it/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/it/) |
| Latviešu (Latvian) | lv | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/lv/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/lv/) |
| Magyar (Hungarian) | hu | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/hu/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/hu/) |
| Nederlands (Dutch) | nl | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/nl/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/nl/) |
| Norsk bokmål (Norwegian Bokmål) | nb | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/nb/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/nb/) |
| Polski (Polish) | pl | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/pl/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/pl/) |
| Portuguêse do Brazil (Brazil) | pt_BR | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/pt_BR/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/pt_BR/) |
| Русский (Russian) | ru | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/ru/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/ru/) |
| Suomi (Finnish) | fi | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/fi/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/fi/) |
| Svenska (Swedish) | sv | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/sv/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/sv/) |
| Українська (Ukrainian) | uk | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/uk/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/uk/) |
| 日本語 (Japanese) | ja | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/ja/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/ja/) |
| 中文 (Chinese) | zh_Hans_CN | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/zh_Hans/mapper/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/mapper/zh_Hans/) |

Map symbols are translated to the following languages:

| Language | Code | State |
| -------- | ---- | ----- |
| Čeština (Czech) | cs | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/cd/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/cs/) |
| Dansk (Danish) | da | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/da/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/da/) |
| Deutsch (German) | de | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/de/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/de/) |
| Esperanto | eo | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/eo/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/eo/) |
| Français (French) | fr | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/fr/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/fr/) |
| Nederlands (Dutch) | nl | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/nl/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/nl/) |
| Русский (Russian) | ru | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/ru/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/ru/) |
| Suomi (Finnish) | fi | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/fi/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/fi/) |
| Svenska (Swedish) | sv | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/sv/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/sv/) |
| Українська (Ukrainian) | uk | [![Translation status](https://hosted.weblate.org/widgets/openorienteering/uk/map-symbols/svg-badge.svg)](https://hosted.weblate.org/projects/openorienteering/map-symbols/uk/) |

## Information for Translators

Translation efforts should first focus on standard user interface items such as menu entries, window titles, button labels etc. 

### Translation online with [Weblate](https://hosted.weblate.org/engage/openorienteering/)

<a href="https://hosted.weblate.org/engage/openorienteering/">
<img src="https://hosted.weblate.org/widgets/openorienteering/-/287x66-grey.png" alt="Translation status" />
</a>

Editing translations online on [Weblate](https://hosted.weblate.org/projects/openorienteering/mapper/) is the most convenient way to start contributing. Weblate provides a number of checks and other interesting features. There is an [online translators guide](https://docs.weblate.org/en/latest/user/).

 * Even if not a registered user, you may **add suggestions** which will eventually be accepted or rejected by registered users.
 * You can easily register and login with your Github account. Registered users may set their language and **subscribe for the OpenOrienteering project and for notifications**. This needs to be done in the individual Weblate profile.
 * Registered users can **create and edit translations**, and accept suggestions. Please pay attention to the comments, suggestions and checks for each item.
 * Registered users may **add new comments** to either the source string (e.g. suggestions to fix typos and change punctuation, or requests for clarification), or to the translation for a particular language (discussion with or documentation for other translators).
 * When saving a translation, translators may add a commit message. However you should not use this field unless you know what you are doing. These messages are recorded more or less permanently in the project's revision history.

Unfortunately, there is no easy way to test the translations until they eventually arrive in an unstable build.

OpenOrienteering uses Weblate's free hosting offer for open source projects. You may [donate to Weblate](https://weblate.org/donate/) to support both projects.

#### Special markers in translations

 * **Placeholders:** The source strings may contain placeholders such as `%1` or `%n`.
   `%1`, `%2` etc. are replaced with some text or number when displayed. Since each number identifies a particular spot in the source string, you may change the order the placeholders so that it fits the grammar of the language you translate for.
   `%n` is a special marker which will be replaced with a number. In addition the value of the number is used to select between singular and plural versions of the translation.

 * **Shortcuts:** An ampersand `&` before a letter is used to mark the following letter as a shortcut key. In this case, the ampersand is not displayed, but usually the shortcut is indicated by underlining the letter. You may choose a different letter for the translation.

 * **HTML markup:** Some strings contain HTML markup, such as `<b>...</b>` for <b>bold</b> style. Please try to maintain this markup in the translation.

 * **Line breaks:** Some strings contain line breaks in order to limit the width of some texts or to move certain parts of text to the beginning of a line. Please try to insert similar line breaks in the translation.

----

### Translation offline with Qt Linguist

*Attention: As long as Weblate produces quite different output than the Qt tools (https://github.com/nijel/weblate/issues/1118), it is not recommended to use Qt Linguist: It will lead to some noise in the git change log.*

[Qt Linguist](http://doc.qt.io/qt-5/linguist-translators.html) can be installed as part of the [Qt SDK installer](http://www.qt.io/download-open-source/) or as part of Linux distributions' Qt5 development tools packages (e.g. qttools5-dev-tools). Linguist is also included in our [unstable Windows package](http://download.opensuse.org/repositories/home:/dg0yt/Windows/).

You may either use git to clone our source code repository, or download and extract a [ZIP-Archive of the master branch](https://github.com/OpenOrienteering/mapper/archive/master.zip). For every supported language, there is a .ts-file in the [translations directory](https://github.com/OpenOrienteering/mapper/tree/master/translations/), which contains both the strings to be translated and the actual translations. 

#### New Languages

To start the translation for a new language offline, you can start with the [template .ts-file](https://raw.githubusercontent.com/OpenOrienteering/mapper/master/translations/OpenOrienteering_template.ts). You can submit the new translation with a pull request or an issue on [Github](https://github.com/OpenOrienteering/mapper/). 

#### Updating Translations

To update or modify an existing translation you can download the latest version from the [translations directory](https://github.com/OpenOrienteering/mapper/tree/master/translations/) or use git to checkout the source code including the translations directory: 

~~~
git clone https://github.com/OpenOrienteering/mapper.git
~~~

You can submit the updated translation with a pull request or an issue on [Github](https://github.com/OpenOrienteering/mapper/). 

When the developers add new strings to the source code, these strings have to be added to the the .ts-files. This is done by calling the lupdate program with the proper sources and targets. For platforms where `/bin/sh` is available a script `translations/update-translations.sh` is provided which automates that process. 

**Warning:** Since the .ts-file contains the translated strings, you might loose translations which are not yet in the git repository when you download a fresh copy of the file from the git repository. Make a backup of your work if you are in doubt. For merging translations see below. 

#### Testing Translations

To test your translation, you must generate a .qm file and make it available to your Mapper program. Your can save a .qm file from Qt Linguist. Than it should be enough to put the resulting .qm file to the "translations" subdirectory of the Mapper executable directory, or to select it from the settings dialog. The file must be named OpenOrienteering_YOURLOCALE.qm (e.g. OpenOrienteering_de.qm). The desired language can be chosen in the settings dialog (menu "File" &gt; "Settings..."). 

### Translation Qt

Some strings in the user interface come from the Qt library which is used by Mapper. Examples are the standard dialog buttons (OK, Cancel, Help, etc.) which are used in many places such as the settings dialog. 

Unfortunately, the library's translation is rather incomplete at the moment. So we provide another template which can be used to provide a minimal translation of Qt. The download is here: [template .ts-file](https://github.com/OpenOrienteering/mapper/tree/master/translations/qt_template.ts?format=raw)

  


## Information for Programmers

  * Learn about the [Qt translation framework from a programmer's point of view](http://qt-project.org/doc/qt-5.0/qtlinguist/linguist-programmers.html). 
  * Add `tr("....")` to strings to be translated. In case of UTF-8 characters which are not part of the Latin-1 charset, use `trUtf8("...")` instead. 
  * For standard dialog box buttons, use [`QDialogButtonBox`](http://qt-project.org/doc/qt-5.0/qtwidgets/qdialogbuttonbox.html) with the appropriate [`StandardButtons`](http://qt-project.org/doc/qt-5.0/qtwidgets/qdialogbuttonbox.html#StandardButton-enum). This class will use the platform look and feel, and it removes the necessity to introduce translatable string for standard buttons. 
  * Keep translations in mind when constructing phrases: 
    * Find a good phrase before first commit. 
    * Don't introduce many variants of phrases when standardization is easily possible. 
  * Even units of measurement might need translation. For disambiguation (in addition to the context, supply a second parameter to `tr()`, e.g. 
~~~
tr("m", "meters")
~~~
    

## Maintaining Translations in the Build System

  * Translations (.ts files) shall be saved in the translations directory. 
  * Translations must be added to the `Mapper_TRANS` variable in CMakeLists.txt. 
  * Translations may be updated by calling `make Mapper_translations_update` (for all translations and the template), `make Mapper_OpenOrienteering_XX_update` (for language XX), or `make Mapper_OpenOrienteering_template_update` (for the template only). 

  


## Merging translations

Sometimes it may be useful to merge several translations into a single file, e.g. to provide a single download file which contains both Mapper and Qt translations. This can be achieved with the lconvert tool from the Qt SDK. This is a versatile tool which actually can convert a number of different formats. 
