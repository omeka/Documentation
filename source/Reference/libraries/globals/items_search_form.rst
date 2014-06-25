.. _fitemssearchform:

##################################################################
``items_search_form`` — Return the HTML for an item search form.
##################################################################

:doc:`Search-related functions </Reference/packages/Function/View/Search/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/items_search_form.rst

.. php:function:: items_search_form($props = array(), $formActionUri = null, $buttonText = null)

    Return the HTML for an item search form.
    
    :type $props: array
    :param $props: Custom HTML attributes for the form element
    :type $formActionUri: string
    :param $formActionUri: URL the form should submit to. If omitted, the form submits to the default items/browse page.
    :type $buttonText: string
    :param $buttonText: Custom text for the form submit button. If omitted, the default text 'Search for items' is used.
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/items_search_form.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/items_search_form.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/items_search_form.rst

