.. _search_form:

###########
search_form
###########

*****
Usage
*****

Alter the search form generated in application/views/scripts/search/search-form.php.

*****
Value
*****

``string`` $form
    The HTML of the search form

*********
Arguments
*********

``array`` options
    Options to pass to the form partial as $options
    
``array`` filters
    Filters to pass to the form partial as $filters
    
``array`` query_types
    Query types for the form to make available

``array`` record_types
    Record types for the form to make available