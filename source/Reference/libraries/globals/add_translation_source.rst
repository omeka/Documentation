.. _faddtranslationsource:

###################################################################
``add_translation_source`` — Add an translation source directory.
###################################################################

:doc:`Locale-related functions </Reference/packages/Function/Locale/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/add_translation_source.rst

.. php:function:: add_translation_source($dir)

    Add an translation source directory.
    
    The directory's contents should be .mo files following the naming scheme
    of Omeka's application/languages directory. If a .mo for the current
    locale exists, the translations will be loaded.
    
    :type $dir: string
    :param $dir: Directory from which to load translations.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/add_translation_source.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/add_translation_source.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/add_translation_source.rst

