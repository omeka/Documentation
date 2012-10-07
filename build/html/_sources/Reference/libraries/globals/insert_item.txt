###########
insert_item
###########

.. php:function:: insert_item(array $metadata = Array, array $elementTexts = Array, array $fileMetadata = Array)

    Insert a new item into the Omeka database.
    
    :param array $metadata: Set of metadata options for configuring the item. Array which can include the following properties: <ul> <li>'public' (boolean)</li> <li>'featured' (boolean)</li> <li>'collection_id' (integer)</li> <li>'item_type_id' (integer)</li> <li>'item_type_name' (string)</li> <li>'tags' (string, comma-delimited)</li> <li>'tag_entity' (Entity, optional and only checked if 'tags' is given)</li> <li>'overwriteElementTexts' (boolean) -- determines whether or not to overwrite existing element texts.  If true, this will loop through the element texts provided in $elementTexts, and it will update existing records where possible.  All texts that are not yet in the DB will be added in the usual manner.  False by default.</li> </ul>
    :param array $elementTexts: Array of element texts to assign to the item. This follows the format: <code> array( [element set name] => array( [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ), [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ) ), [element set name] => array( [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ), [element name] => array( array('text' => [string], 'html' => [false|true]), array('text' => [string], 'html' => [false|true]) ) ) ); </code>
    :param array $fileMetadata: Set of metadata options that allow one or more files to be associated with the item.  Includes the following options: <ul> <li>'file_transfer_type' (string = 'Url|Filesystem|Upload' or Omeka_File_Transfer_Adapter_Interface). Corresponds to the $transferStrategy argument for addFiles().</li> <li>'file_ingest_options' OPTIONAL (array of possible options to pass modify the behavior of the ingest script).  Corresponds to the $options argument for addFiles().</li> <li>'files' (array or string) Represents information indicating the file to ingest. Corresponds to the $files argument for addFiles().</li> </ul>
    :returns: Item

*****
Usage
*****



********
Examples
********



