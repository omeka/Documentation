.. _finsertcollection:

#############################################
``insert_collection`` — Insert a collection
#############################################

:doc:`Collection-related functions </Reference/packages/Function/Db/Collection/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/insert_collection.rst

.. php:function:: insert_collection($metadata = array(), $elementTexts = array())

    Insert a collection
    
    :type $metadata: array
    :param $metadata: Follows the format: <code> array( 'public'      => [true|false], 'featured'    => [true|false] ) </code>
    :type $elementTexts: array
    :param $elementTexts: Array of element texts to assign to the collection. This follows the format: <code> array( [element set name] => array( [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ), [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ) ), [element set name] => array( [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ), [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ) ) ); </code>
    :returns: Collection

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/insert_collection.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/insert_collection.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/insert_collection.rst

