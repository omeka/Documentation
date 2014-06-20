##########################
Plugin Directory Structure
##########################

**********
The basics
**********

There are a few things that any plugin must contain: the plugin folder, the plugin
INI file, and the main plugin PHP file.

=============
Plugin folder
=============

An Omeka plugin must have one top-level folder that all the other folders and files
are contained in. This folder is what users end up putting in their installation's
:file:`plugins/` directory.

Omeka uses the folder names to keep track of which plugins are installed and
activated, so once you pick a folder name, you should stick with it. The folder
name also determines things like the default URLs that will be used if your
plugin adds pages of its own.

There are a few principles you should keep in mind when picking a plugin folder name.
The name should be:

* **Unique**: the name must not conflict with an existing plugin name
* **Simple**: the name should be concise and to-the-point
* **Descriptive**: the name should describe the plugin, at least to some degree
* **CamelCased**: the name must contain no spaces, and the first letter of every
  "word" should be capitalized (e.g.: ``SimplePages``, ``ExhibitBuilder``)

In addition, the human-readable name you set in the plugin.ini should usually
be the "normal" equivalent of your folder name, so users can easily tell which
folder goes with which plugin.

================
Main plugin file
================

The most important file in most plugins is the main plugin file. This is the file Omeka
actually loads when loading the plugin, and its where all the hooks and filters are
registered and defined.

The main plugin file must have the same name as the plugin folder, with ``Plugin.php``
tacked onto the end. For example, a plugin in the folder :file:`Foo` will have a
main plugin file named :file:`FooPlugin.php`.

The :file:`FooPlugin.php` file must contain a PHP class with the same name (without the
``.php``). Generally, this class will be a subclass of
:php:class:`Omeka_Plugin_AbstractPlugin`. For more information about how to write and use
a main plugin class, see :doc:`understandingOmeka_Plugin_AbstractPlugin`.

.. note::
   Omeka also supports another, older, type of main plugin file, at :file:`plugin.php`.
   This file is plain PHP code and is not required to contain a class. Current plugins
   mostly use the class-based main file, however.

========================================
Plugin information file (``plugin.ini``)
========================================

The INI file for the plugin, :file:`plugin.ini` is used both by Omeka itself and
the plugin directory on omeka.org. Most of what the INI file contains is
metadata about the plugin, like the name of the plugin, the author, and a
description. However, some fields are internally used by Omeka when loading
the plugin.

The first line in any plugin.ini file should be ``[info]``. The rest of the file
consists of various fields, one on each line. The possible fields are:

name
    The name of the plugin.
author
    The plugin's author.
description
    A short description of the plugin.
version
    The plugin's version number. Omeka uses this to determine when a user has
    upgraded a plugin.
license
    The software license the plugin is released under. This key is used by the 
    plugins directory on omeka.org.
link
    A URL for information or documentation about the plugin.
support_link
    A URL for users to go to for help with the plugin or to report an issue.
omeka_minimum_version
    The minimum version of Omeka needed to run the plugin. Omeka will refuse to
    install or load any plugin that requires a higher Omeka version.
omeka_target_version
    The most recent version the plugin is intended to work on and was tested on.
    Omeka itself does not report or use this value, but it does appear on the 
    omeka.org plugin directory.
required_plugins
    Other plugins that *must* be installed for the plugin to work. Plugins must be
    specified by their folder names, and multiple required plugins are separated by
    commas. Omeka will refuse to load the plugin if any of the required plugins are
    missing, and will make sure the plugin loads after all plugins it requires.
optional_plugins
    Other plugins that the plugin *can* work with. Plugins must be specified by their
    folder names, and multiple required plugins are separated by commas. Omeka will
    make sure the plugin loads after all plugins it requires.

Here is an example plugin.ini that uses all the possible fields:

.. code-block:: ini

    [info]
    name = "Foo"
    author = "My Name"
    description = "Does this, that, and the other thing."
    version = "1.0"
    license = "GPLv3"
    link = "http://example.com/my-plugin"
    support_link = "http://example.com/my-plugin/support"
    omeka_minimum_version = "2.0"
    omeka_target_version = "2.2"
    required_plugins = "ExhibitBuilder,SimplePages"
    optional_plugins = "Bar,Baz"
