#############
api_resources
#############

.. versionadded:: 2.1

*****
Usage
*****

Allows plugins to add their content to the Omeka API

*****
Value
*****

``array`` $apiResources
   An array of the resources registered with the API
   
*********
Arguments
*********

None


********
Examples
********


.. code-block:: php

    <?php
    protected $_filters = array('api_resources');

    public function filterApiResources($apiResources)
    {
        $apiResources['geolocations'] = array(
            'record_type' => 'Location', 
            'actions' => array('get', 'index', 'post', 'put', 'delete'), 
        );
        return $apiResources;
    }
    
 See also :doc:`/Reference/api/extending`
