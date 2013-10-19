# Introduction
The devhelp2qhp is simple utility written in Python to convert the gtk-doc
generated .devhelp2 file into .qhp (Qt Project Help) file which can be then via
qhelpgenerator (part of Qt toolkit) turned into a .qch (Qt Compressed Help) and
used with Qt Assistant or Qt Creator.

# Requirements
* Python 2.7 (should also work with lower versions)

# Install
* Extract the zip
* Make sure the devhelp2qhp is executable
* For convenience put the utility into your $PATH

# Usage example
Get a documentation package using gtk-doc e.g. GObject.
From http://developer.gnome.org/gobject/ download the latest version (as of
writing this http://developer.gnome.org/gobject/gobject-html-2.34.3.tar.gz)

Extract the archive and cd into the directory containing the documentation.

Do get devhelp2qhp usage help
    $> devhelp2qhp -h

Do generate a .qhp file
    $> devhelp2qhp gobject.devhelp2 org.gnome.developer.gobject 2.34.3

The gobject.qhp will be created in the same directory. To compile the .qch
    $> qhelpgenerator gobject.qhp -o gobject-2.34.3.qch
