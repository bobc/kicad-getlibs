KiCad-GetLibs
=============

A tool for downloading and installing kiCad packages. May require KiCad v5.

Runs on Windows, Linux (MacOs might work).

Description
-----------

Currently supports footprints, symbols and templates. Configurations for KiCad
official v5 libraries and templates, SparkFun, DigiKey and Walter Lain libraries.

Where available, point releases are downloaded as a zip file. Otherwise, latest
versions of git repositories are cloned locally.

This script uses git to:

1. Clone a repository if you don't have it
2. Pull the latest repository if you already have it locally (does an update).

. Footprints can be installed to fp-lib-table.
. Symbols can be installed to sym-lib-table.
. Templates are copied to $USER/kicad/template
. 3dmodels TODO
. Scripts TODO

Existing xx-lib-table will be saved to xx-lib-table-old.

Usage
-----

`python kicad-getlibs.py [options] <package file> [<version>]`

Package file contains the packages to download/install.
Version is a valid version from the package file or "latest".

Options are:

-h, --help  Shows a help screen on the command line

-v, --verbose  Shows the verbose messages

-q, --quiet  Don't show logging

-c, --config <local folder>  Configure get-libs
      The local folder is the folder you want all your local data put in.

-d, --download Download package data only

-i, --install  Install package data into KiCad (implies download)

-u, --uninstall   Uninstall package data from KiCad


**Example Usage**

    python kicad-getlibs.py -c c:\kicad_data
    python kicad-getlibs.py -vi kicad-official-libraries-v5.yml

**Dependencies**

- You need to have git installed

Otherwise it should just run with a standard distribution of python 2.x, there
are no special libraries used.

Bugs/Feature Requests
----------------------

Please raise issue on github.

