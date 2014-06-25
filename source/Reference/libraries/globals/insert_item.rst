.. _finsertitem:

##############################################################
``insert_item`` — Insert a new item into the Omeka database.
##############################################################

:doc:`Item-related functions </Reference/packages/Function/Db/Item/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/insert_item.rst

.. php:function:: insert_item($metadata = array(), $elementTexts = array(), $fileMetadata = array())

    Insert a new item into the Omeka database.
    
    :type $metadata: array
    :param $metadata: Set of metadata options for configuring the item. The array can include the following properties: - 'public' (boolean) - 'featured' (boolean) - 'collection_id' (integer) - 'item_type_id' (integer) - 'item_type_name' (string) - 'tags' (string, comma-delimited) - 'overwriteElementTexts' (boolean) -- determines whether or not to overwrite existing element texts.  If true, this will loop through the element texts provided in $elementTexts, and it will update existing records where possible.  All texts that are not yet in the DB will be added in the usual manner.  False by default.
    :type $elementTexts: array
    :param $elementTexts: Array of element texts to assign to the item. This follows the following format:: array( [element set name] => array( [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ), [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ) ), [element set name] => array( [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ), [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ) ) );
    :type $fileMetadata: array
    :param $fileMetadata: Settings and data used to ingest files into Omeka and add them to this item.  Includes the following options: - 'file_transfer_type' (string = 'Url|Filesystem|Upload' or Omeka_File_Transfer_Adapter_Interface). Corresponds to the $transferStrategy argument for addFiles(). - 'file_ingest_options' (array) Optional array of options to modify the behavior of the ingest.  Corresponds to the $options argument for addFiles(). - 'files' (array or string) Represents information indicating the file to ingest. Corresponds to the $files argument for addFiles().
    :returns: Item

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/insert_item.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/insert_item.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/insert_item.rst

