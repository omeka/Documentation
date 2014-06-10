#####################
api_extend_<resource>
#####################

.. versionadded:: 2.1

*****
Usage
*****

Extends an existing resource registered with the API. If your plugin creates content related to items,
for example, use this to add that data to an item's representation. ``<resource>`` is the name of the resource,
e.g. ``items``

*****
Value
*****

``array`` $extend 

   Array of representations that extend the resource
   
*********
Arguments
*********

:php:class:`Omeka_Record_AbstractRecord` record

   The record whose representation in the API you are extending
   
********
Examples
********

.. code-block:: php

    public function filterApiExtendItems($extend, $args)
    {
        $item = $args['record'];
        $location = $this->_db->getTable('Location')->findBy(array('item_id' => $item->id));
        if (!$location) {
            return $extend;
        }
        $locationId = $location[0]['id'];
        $extend['geolocations'] = array(
            'id' => $locationId, 
            'url' => Omeka_Record_Api_AbstractRecordAdapter::getResourceUrl("/geolocations/$locationId"), 
        );
        return $extend;
    }

See also :doc:`/Reference/api/extending`    
