######################
add_translation_source
######################

*******
Summary
*******

.. include:: summary/add_translation_source.rst

.. php:function:: add_translation_source(string $dir)

    Add an translation source directory.
    
    The directory's contents should be .mo files following the naming scheme of Omeka's application/languages directory.
    If a .mo for the current locale exists, the translations will be loaded.
    
    :param string $dir: Directory from which to load translations.

*****
Usage
*****

.. include:: usage/add_translation_source.rst

********
Examples
********

.. include:: examples/add_translation_source.rst

********
See Also
********

.. include:: see_also/add_translation_source.rst

