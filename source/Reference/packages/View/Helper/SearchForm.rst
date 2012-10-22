----------------------------
Omeka_View_Helper_SearchForm
----------------------------

.. php:class:: Omeka_View_Helper_SearchForm

    Package: :doc:`/Reference/packages/View\Helper/index`

    Return the site-wide search form.

    .. php:attr:: _validQueryTypes
    


    .. php:attr:: _validRecordTypes
    


    .. php:method:: __construct()
    
        Set the valid query and record types.

    .. php:method:: searchForm(array $options = Array)
    
        Return the site-wide search form.
        
        :param array $options: Valid options are as follows: - show_advanced: whether to show the advanced search; default is false. - submit_value: the value of the submit button; default "Submit". - form_attributes: an array containing form tag attributes.
        :returns: string The search form markup.

    .. php:method:: _parseOptions(array $options)
    
        Set default options if not passed to this helper.
        
        :param array $options: 
        :returns: array

    .. php:method:: _parseRequest()
    
        Set default form values if not passed with the request.
        
        :returns: array