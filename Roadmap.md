**Warning**: this is partly out of date. For more current information, have a look at the [issues](https://github.com/OpenOrienteering/mapper/issues). 

**Milestone 1**:  
Make basic map drawing possible using Mapper on the desktop 

  * Main drawing tools: 
    * Circles 
    * Ellipses 
    * Rectangles 
    * Text 
  * View tools: 
    * Center view on map 
    * Set custom zoom factor 
  * Important editing tools: 
    * Cut, Copy, Paste 
    * Add / remove points on paths 
    * Snapping for editing tools 
      * Following existing paths and appending to existing paths with the path draw tool 
    * Cut objects 
    * Connect lines 
    * Cut holes into objects 
    * Rotate objects 
    * Close / connect paths 
    * Measure distances 
  * Important map operations: 
    * Rotate map 
    * Import other map 
    * Exchange symbol set 
  * Symbol browser operations: 
    * Sort symbols 
    * Hiding and protecting symbols 
    * Copy, Paste 
    * Select unused symbols 
  * “Problem widget” showing 
    * Templates which are not found 
    * Objects which do not meet the minimum size determined by their symbol 
  * Build ISSOM symbol set 
  * OC*D file import 
    * Version 8 
    * Version 10 
  * OC*D file export, version 8 

  
**Milestone 2**:  
Provide an Android version of Mapper with an adapted user interface to support surveying 

  * Evaluate the Necessitas (Qt on Android) project, determine if it supports everything the application needs and works stable 
  * Design the mobile user interface 
  * Implement the mobile user interface 
  * Implement surveying features 
    * Enable rotating the map based on a digital compass sensor and determine if its precision is sufficient 
    * Read values from the internal GPS unit 
      * Display the current position on the map 
      * Center the map on the current position 
      * Draw helper lines (e.g. in 10m steps around the current position, a circle displaying the GPS positioning certainty, straight forward line, …) 
    * Read values from an external GPS unit connected via bluetooth 
    * Average current position and set point object there 
    * Definition and use of template configurations to quickly switch between multiple templates 
    * Implement taking georeferenced photos 

  
**Milestone 3**:  
Add less important features and polishing and release a stable version 1.0 

  * Fixed angles for editing tools 
  * Scale and rotate arrows for the move tool 
  * Color correction (plus, add an option for export to image to include it there or not) 
  * Layer management 
  * Object grouping 
  * Multiple viewport support 
  * Helper grid 
  * Hiding all templates 
  * Make shortcuts adjustable, implement program settings 
  * GPS window for the desktop version 
  * Advanced template types 
    * Map templates 
    * Sketch templates 
    * Laserscan templates 
  * Template grouping 
  * “Move by hand” for templates 
  * Numeric transformation window for templates 
  * Numeric transformation window for objects 
  * Image template operations: trace lines, make color transparent 
  * Less important drawing tool: 
    * Numeric object creation tool 
  * Less important editing tools: 
    * Change all symbols of one type to another 
    * Change layer of objects 
    * Round corners of rectangle 
    * Grow/Shrink object based on curve normals 
    * Union of objects 
    * Intersection of objects 
    * Difference of objects 
    * Distribute object on path 
    * Interpolate paths 
    * Subdivide path 
    * Get GPS coordinates for location 
  * Less important map operations: 
    * Create excerpt 
  * Make a legend object type to simplify the creation of legends and give a warning for objects where a legend entry is required but does not exist 
  * Write documentation and create in-application help 
