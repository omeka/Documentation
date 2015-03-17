###########
search_form
###########

*****
Usage
*****

Alter the sitewide search form created by :php:func:`search_form`.

The original form can be altered, added to, or replaced using this filter.

*****
Value
*****

``string`` $form
    The HTML of the search form

*********
Arguments
*********

``array`` options
    Options passed to the form partial as $options
    
``array`` filters
    Filters passed to the form partial as $filters
    
``array`` query_types
    Query types for the form to make available

``array`` record_types
    Record types for the form to make available
