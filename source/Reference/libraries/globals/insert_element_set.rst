.. _finsertelementset:

##################
insert_element_set
##################

:doc:`ElementSet-related functions </Reference/packages/Function/Db/ElementSet/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/insert_element_set.rst

.. php:function:: insert_element_set(string|array $elementSetMetadata = Array, array $elements = Array)

    Insert an element set and its elements into the database.
    
    :param string|array $elementSetMetadata: Element set information.         
    
        .. code-block:: php 
    
    
             [(string) element set name]
             // OR
             array(
               'name'        => [(string) element set name, required, unique],
               'description' => [(string) element set description, optional],
               'record_type' => [(string) record type name, optional]
             );
     
    :param array $elements: An array containing element data. Follows one of more of the following formats:         
    
        .. raw:: html
    
           <ol>
             <li>An array containing element metadata</li>
             <li>A string of the element name</li>
             </ol>
             
    
        .. code-block:: php 
    
    
             array(
               array(
                 'name' => [(string) name, required],
                 'description' => [(string) description, optional],
               ),
               [(string) element name]
             );
     
    :returns: ElementSet

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/insert_element_set.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/insert_element_set.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/insert_element_set.rst

