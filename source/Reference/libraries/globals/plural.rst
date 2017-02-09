.. _fplural:

###############################################################
``plural`` — Transform arguments in an array suitable for __.
###############################################################

:doc:`Locale-related functions </Reference/packages/Function/Locale/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/plural.rst

.. php:function:: plural($msgid, $msgid_plural, $n)

    Transform arguments in an array suitable for __.
    
    <code>
    $n = count($items);
    echo __(plural('one item', '%s items', $n), $n);
    </code>
    
    :type $msgid: string
    :param $msgid: The string to be translated, singular form
    :type $msgid_plural: string
    :param $msgid_plural: The string to be translated, plural form
    :type $n: int
    :param $n: Used to determine the plural form
    :returns: array Array to pass to __

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/plural.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/plural.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/plural.rst

