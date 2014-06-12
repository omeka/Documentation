######################
file_ingest_validators
######################

*****
Usage
*****

Allows you to add or remove validators to be used when a file is uploaded.

*****
Value
*****

``array`` $validators
    A keyed array of validators to use. Validators are subclasses of Zend_Validate_Abstract.

*********
Arguments
*********

None

********
Examples
********

The default validators are:

.. code-block:: php

    array(
          'extension whitelist'=> new Omeka_Validate_File_Extension,
          'MIME type whitelist'=> new Omeka_Validate_File_MimeType
        )

        
To swap out Omeka's Mime Type validator for your own:

.. code-block:: php

    public function filterFileIngestValidators($validators)
    {
        unset($validators, 'MIME type whitelist');
        $validators['my mime validator'] = new MyPlugin_Validate_File_MimeType;
        return $validators;    
    }
    
    
           
