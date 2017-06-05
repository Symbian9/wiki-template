This page roughly sums up the required steps to make a new release of OpenOrienteering Mapper. 

  


## Preparations

Code: 

  * Verify the INSTALL.md instructions file. 
  * Tag (vX.Y.Z-RC1) and build release candidates from the master branch.
  * Merge the final state of the master branch to the release branch,
    and tag the release there (vX.Y.Z).
    * After this, bump the version number in CMakeLists.txt in the master branch.
      Build once in order to push the version number to additional files,
      and commit and push the version number change.

Packages:

  * The source archive is provided by Github once it received a tag.
  * The superbuild repository shall get a new release if there are major changes to the sources (e.g. Qt).
  * Binary packages for macOS and Android can be uploaded to the draft release.
  * Binary packages for Windows and Linux can be build in the staging project on OBS.

## Release

  * Publish the staged package on OBS.
  * Publish the release draft, including the uploaded binary packages.
  * Publish a release announcement blog post.
  * Update the Mapper app page.
    * Update the version numbers in the frontmatter.
    * Update the release announcement blog post link.
    * Add the new release to the list of all releases.

## Extra announcements

Short release announcements may be posted to the following sites: 
   1. English: 
      1. International: http://groups.yahoo.com/group/O-Map/ 
      2. International: http://www.attackpoint.org/discussion.jsp?refs=6.1+1.0 
      3. Great Britain: http://forum.nopesport.com/ 
   2. German: 
      1. Germany: http://www.orientierungslauf.de/2/1 
      2. Germany: http://ardf.darc.de/forum/ 
      3. Austria: http://ol-sport.at/discussions 
      4. Switzerland: http://www.swiss-orienteering.ch/forum.php 


