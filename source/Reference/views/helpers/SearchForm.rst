----------------------------
Omeka_View_Helper_SearchForm
----------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_SearchForm

extends :php:class:`Zend_View_Helper_Abstract`

    Return the site-wide search form.

    .. php:method:: searchForm($options = array())

        Return the site-wide search form.

        :type $options: array
        :param $options: Valid options are as follows: - show_advanced: whether to show the advanced search; default is false. - submit_value: the value of the submit button; default "Submit". - form_attributes: an array containing form tag attributes.
        :returns: string The search form markup.
