----------------------------
Omeka_View_Helper_SearchForm
----------------------------

.. php:class:: Omeka_View_Helper_SearchForm

    Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

    Return the site-wide search form.

    .. php:method:: searchForm(array $options)
    
        Return the site-wide search form.
        
        :param array $options: Valid options are as follows: - show_advanced: whether to show the advanced search; default is false. - submit_value: the value of the submit button; default "Submit". - form_attributes: an array containing form tag attributes.
        :returns: string The search form markup.