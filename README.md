Lizmap - Documentation
=======================

This repository contains the complete documentation of the Lizmap application to publish online QGIS maps: the QGIS plugin and Lizmap Web Client application.

This documentation uses **Sphinx** (http://sphinx-doc.org) and its internationalization mechanism (http://sphinx-doc.org/intl.html):
* **source** contains the documentation in \*.rst format
* **i18n** contains the locals

Contribution
=============

* Update documentation by updating **source** files
* Localize documentation by updating your langage in **i18n** or adding ones.

Update localized files
=======================

* Update pot files from source files

```
sphinx-build -b gettext source i18n/pot
```

* Update localized files (*.po)

```
sphinx-intl update -d i18n
```

Then you can improve po files by opening them with QtLinguist.

Build documentation
====================

We advise to use the **make** command to build Sphinx documentation. Here are some examples:

```

# Generate mo files by building freshly modified po files
sphinx-intl build -d i18n

# Build documentation in english (default language) in HTML format
make html BUILDDIR=build/latex/en

# Build documentation in french in HTML
make html BUILDDIR=build/latex/fr SPHINXOPTS="-D language='fr'"

# Build PDF in english
make latexpdf BUILDDIR=build/latex/en

# Build PDF in french
make latexpdf BUILDDIR=build/latex/fr SPHINXOPTS="-D language='fr'"

```
