This page roughly sums up the required steps to make a new release of OpenOrienteering Mapper. 

  


## Preparations

Code: 

  * Create a new git branch for the release if it is a feature release (change in minor version component). The name shall be vMAJOR.MINOR. 
  * In the release branch, set the correct version number in CMakeLists.txt. 
  * Verify the INSTALL instructions file. 

Files: 

  * Create a source package - this is required! Call "make Mapper_Source" from a clean checkout of the release branch. 
  * Create binary packages for all supported systems from that source package. 
  * Prepare a README file to be displayed at the bottom of the files view. 
  * Upload the files in a staged folder on SourceForge. Don't forget 3rd-party sources. 

Web: 

  * Make a backup and update the Wordpress version of the blog ( http://oorienteering.sourceforge.net/ ), including plugins 
  * Prepare the release announcement (long version for blog and short versions for ads on various websites) 

## Release

  1. Remove staging flag from release folder 
  2. Adapt readme file in main directory 
  3. Publish release announcement on blog 
  4. Update Mapper page in blog ( http://oorienteering.sourceforge.net/?page_id=103 ) 
  5. Post short release announcements to the following sites: 
    1. English: 
      1. International: http://groups.yahoo.com/group/O-Map/ 
      2. International: http://www.attackpoint.org/discussion.jsp?refs=6.1+1.0 
      3. Great Britain: http://forum.nopesport.com/ 
    2. German: 
      1. Germany: http://www.orientierungslauf.de/2/1 
      2. Germany: http://ardf.darc.de/forum/ 
      3. Austria: http://ol-sport.at/discussions 
      4. Switzerland: http://www.swiss-orienteering.ch/forum.php 
  6. Send notification with links to all ad posts at the above sites to the mailing list 
  7. Update Mapper SourceForge Home page ( http://sourceforge.net/p/oorienteering/home/Home/ ) 
  8. Make another backup of the blog 

  


## Afterwards

  * Tag the git commit which was used to create the release 
