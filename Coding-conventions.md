This is a list of coding conventions used by the OpenOrienteering Mapper project, roughly ordered by importance. It is not demanded to obey these rules slavishly, but most of all when changing existing code they should help to retain a clear formatting. 

Not a coding convention, but also important: please make sure to call QObject::tr() on all strings which should be made translatable. You have to do this on the raw strings, not variables, because the translation process involves running a tool on the source files to find out the translatable strings which works only if the method is used this way. 

**File names**:  
Lowercase with words separated by underscores, for example "some_project_file.cpp" 

**Indentation**:  
Use tabs with a width of 4 

**Naming**:  
Variable names are lowercase and words are separated with underscores, method and class names are in camel case. Methods start with a lowercase letter, class names with an uppercase letter. 
    
    class ExampleClass
    {
    public:
        void getSomethingDone();
        float makeCrazier();
    
    private:
        int some_integer;
        float degree_of_craziness;
    }
    

**Braces**:  
Normally opened on the next line, except in a few cases. Examples: 
    
    // Normal case
    if (random)
    {
        cutGreenWire();
        explode();
    }
    else
    {
        cutRedWire();
        implode();
    }
    
    // Special case
    inline void veryShortMethod() {veryShortContent();}
    

**Exceptions**:  
Are not used, error handling is done via return values. 

_Less important stuff_: 

**Includes**:  
Are separated into up to four blocks: 

  * for source files, the include for the respective header 
  * includes of C++ headers 
  * includes of third party headers 
  * includes of other project headers 

Inside the blocks, there are no rules for ordering. 

Example for a file called "this_file.cpp" 
    
    #include "this_file.h"
    
    #include &lt;string.h&gt;
    #include &lt;assert.h&gt;
    
    #include &lt;QtGui&gt;
    #include &lt;liblas/liblas.hpp&gt;
    
    #include "map.h"
    #include "map_widget.h"
    

**Containers**:  
The existing code prefers STL containers over Qt containers, but you can use whatever fits better, for example QHash could be a reason to use a Qt container. 
