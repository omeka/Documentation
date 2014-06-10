#####
Hooks
#####

Hooks are one of the main ways plugins can alter and extend Omeka. This page is a
reference list of all the available hooks Omeka provides for plugins to use. See
:doc:`/Tutorials/understandingHooks` for general information about using hooks in
plugins.

*********
All Hooks
*********

.. toctree::
    :glob:
    :maxdepth: 1
    
    *
    
***************
Plugin-specific
***************

.. toctree::
   :maxdepth: 1

   activate
   config
   config_form
   deactivate
   install
   uninstall
   upgrade

***********
Application
***********

.. toctree::
    :glob:
    :maxdepth: 1
    
    initialize
    define_acl
    define_routes

********
Database
********

.. toctree::
    :glob:
    :maxdepth: 1
    
    <model>_browse_sql
    add_<model>_tag
    after_ingest_file
    make_*
    remove_<model>_tag
    

*******
Records
*******

.. toctree::
    :glob:
    :maxdepth: 1
    
    *<model>*
    *record*

Item Records
============

.. toctree::
    :glob:
    :maxdepth: 1
    
    *item*
    
Collection Records
==================


.. toctree::
    :glob:
    :maxdepth: 1
    
    *collections*



*****
Users
*****

.. toctree::
    :glob:
    :maxdepth: 1
    
    *user*
    
    

***********
Admin Theme
***********

.. toctree::
    :glob:
    :maxdepth: 1
    
    admin*
    browse_<model>
    show_<model>


************
Public Theme
************

.. toctree::
    :glob:
    :maxdepth: 1
    
    browse_<model>
    public*
    show_<model>
