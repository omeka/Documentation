##################
insert_element_set
##################

.. php:function:: insert_element_set(string|array $elementSetMetadata = Array, array $elements = Array)

    Insert an element set and its elements into the database.
    
    :param string|array $elementSetMetadata: Element set information. <code> [(string) element set name] // OR array( 'name'        => [(string) element set name, required, unique], 'description' => [(string) element set description, optional], 'record_type' => [(string) record type name, optional] ); </code>
    :param array $elements: An array containing element data. Follows one of more of the following formats: <ol> <li>An array containing element metadata</li> <li>A string of the element name</li> </ol> <code> array( array( 'name' => [(string) name, required], 'description' => [(string) description, optional], ), [(string) element name] ); </code>
    :returns: ElementSet

*****
Usage
*****



********
Examples
********



