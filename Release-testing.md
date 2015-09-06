Checklist for testing release candidate packages: 

  * **Opening Maps**
    * File formats for opening: *.omap *.xmap *.ocd 
    * All supported file formats included in pseudo-type "All maps". 
    * Each supported file format is selectable as distinct file type. 
    * Existing files for all supported listed in file-open dialog. 
    * Opening actually working for existing files: 
      * .omap: both pre-0.5 (binary) map files and current (XML) map files. 
      * .xmap: both old and current XML files. 
      * .ocd: files from OC*D 8 
  * **Saving Maps**
    * File formats for saving: *.omap *.xmap *.ocd 
    * No pseudo-type "All maps". 
    * Each supported file format is selectable as distinct file type. 
    * Default file type is "OpenOrienteering Mapper". 
    * An extension for the file type is properly added to the file name if it is missing. 
    * Existing files for all supported listed in file-save dialog. 
    * Saved files can be loaded again after a program restart 
    * Re-loaded (saved) files can be saved again in a binary identical file. 
    * .xmap files are pretty-formatted, .omap files are compact. 
  * **Importing**
    * File formats for import: *.omap *.xmap *.ocd ... 
    * ... 
  * **Templates**
    * File formats for templates: *.omap *.xmap *.ocd ... 
    * ... 
  * **Editing**
    * Copy and Paste in the same map 
    * Copy and Paste between different maps of the same symbol set 
    * Copy and Paste between a map and a completely empty map (i.e. w/o symbols and colors) 
    * ... 
  * **Printing and Export**
    * Dialog settings, map editor tool and preview for map area in single page and custom area mode. 
    * Dialog settings, map editor tool and preview for page overlap in multi-page configuration. 
    * Dialog settings and preview for resolution 
    * Dialog settings and preview for different scale 
    * Dialog settings and preview for grid 
    * Dialog settings and preview for templates 
    * Dialog settings and preview for overprinting simulation 
    * Map area resizing and preview in different-scale configuration 
    * Tests prints in selected configurations 

... 
