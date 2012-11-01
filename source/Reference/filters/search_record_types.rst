###################
search_record_types
###################



********
Examples
********

.. code-block:: php

    class SimplePagesPlugin extends Omeka_Plugin_AbstractPlugin
    {
    
        /**
         * Add SimplePagesPage as a searchable type.
         */
        function filterSearchRecordTypes($recordTypes)
        {
            $recordTypes['SimplePagesPage'] = __('Simple Page');
            return $recordTypes;
        }    
    }