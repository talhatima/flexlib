# Introduction #

An ANT build script is provided to make building and interacting with the FlexLib project easier.

**TODO** Explain the "test", "lib" and "examples" build targets, as well as "zip" for creating a distribution.  Explain how to edit the manifest.xml file for creating the .swc in the "lib" target.


## Generating Documentation ##

To generate updated ASDoc documentation, run the _doc_ build target.  This will document all of the classes under the _src_ tree.

**Important:** The ASDoc documentation is stored in the SVN repository.  In order to be able to view the documentation in a web browser, the proper mime-types must be set for the files.  There are two ways to do this.

  1. Change your Subversion config file to enable auto-props, or,
  1. Run the _fixDocMimeTypes_ build target

I recommend the first method.  Here are the details of each:

### Enabling Subversion Auto-Props ###

Open your Subversion _config_ file in a text editor.  The file locations are as follows:

  * Windows:  C:\Documents and Settings\

&lt;user&gt;

\Application Data\Subversion\config
  * OS X: ?
  * Linix: ~/.subversion/config

Add the following text at the very end of the file:

```
[miscellany]
enable-auto-props = yes

[auto-props]
# Scriptish formats
*.bat        = svn:eol-style=native; svn:keywords=Id; svn-mine-type=text/plain
*.bsh        = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/x-beanshell
*.cgi        = svn:eol-style=native; svn:keywords=Id; svn-mine-type=text/plain
*.cmd        = svn:eol-style=native; svn:keywords=Id; svn-mine-type=text/plain
*.js         = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/javascript
*.php        = svn:eol-style=native; svn:keywords=Id Rev Date; svn:mime-type=text/x-php
*.pl         = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/x-perl; svn:executable
*.pm         = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/x-perl
*.py         = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/x-python; svn:executable
*.sh         = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/x-sh; svn:executable

# Image formats
*.bmp        = svn:mime-type=image/bmp
*.gif        = svn:mime-type=image/gif
*.ico        = svn:mime-type=image/ico
*.jpeg       = svn:mime-type=image/jpeg
*.jpg        = svn:mime-type=image/jpeg
*.png        = svn:mime-type=image/png
*.tif        = svn:mime-type=image/tiff
*.tiff       = svn:mime-type=image/tiff

# Data formats
*.pdf        = svn:mime-type=application/pdf
*.avi        = svn:mime-type=video/avi
*.doc        = svn:mime-type=application/msword
*.eps        = svn:mime-type=application/postscript
*.gz         = svn:mime-type=application/gzip
*.mov        = svn:mime-type=video/quicktime
*.mp3        = svn:mime-type=audio/mpeg
*.ppt        = svn:mime-type=application/vnd.ms-powerpoint
*.ps         = svn:mime-type=application/postscript
*.psd        = svn:mime-type=application/photoshop
*.rtf        = svn:mime-type=text/rtf
*.swf        = svn:mime-type=application/x-shockwave-flash
*.tgz        = svn:mime-type=application/gzip
*.wav        = svn:mime-type=audio/wav
*.xls        = svn:mime-type=application/vnd.ms-excel
*.zip        = svn:mime-type=application/zip

# Text formats
.htaccess    = svn:mime-type=text/plain
*.css        = svn:mime-type=text/css
*.dtd        = svn:mime-type=text/xml
*.html       = svn:mime-type=text/html
*.ini        = svn:mime-type=text/plain
*.sql        = svn:mime-type=text/x-sql
*.txt        = svn:mime-type=text/plain
*.xhtml      = svn:mime-type=text/xhtml+xml
*.xml        = svn:mime-type=text/xml
*.xsd        = svn:mime-type=text/xml
*.xsl        = svn:mime-type=text/xml
*.xslt       = svn:mime-type=text/xml
*.xul        = svn:mime-type=text/xul
*.yml        = svn:mime-type=text/plain
CHANGES      = svn:mime-type=text/plain
COPYING      = svn:mime-type=text/plain
INSTALL      = svn:mime-type=text/plain
Makefile*    = svn:mime-type=text/plain
README       = svn:mime-type=text/plain
TODO         = svn:mime-type=text/plain

# Code formats
*.c          = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/plain
*.cpp        = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/plain
*.h          = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/plain
*.java       = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/plain
*.as         = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/plain
*.mxml       = svn:eol-style=native; svn:keywords=Id; svn:mime-type=text/plain
```


Now, any time you commit to a Subversion repository, the mime-types will automatically be set for certain file types.  This allows you to view the documentation correctly in a web browser.

### Fixing the mime-type with ANT ###

After you generate the documentation, do an SVN commit so that the files are added to the repostiry.  Run the _fixDocMimeTypes_ build target.  This will loop over all of the documentation files and set the correct mime-types.  When the build completes, do another SVN commit to push the mime-type changes to the repository.