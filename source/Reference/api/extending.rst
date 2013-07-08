#################
Extending the API
#################


Registering Your Resource
-------------------------

You can extend the API to include custom resources. Most resources are
correlated to Omeka records, but you may include non-record resources as
well. In your plugin class, register your resource using the
``api_resources`` filter, following this format:

.. code-block:: php

    <?php
    protected $_filters = array('api_resources');

    public function filterApiResources($apiResources)
    {
        // For the resource URI: /api/your_resources/[:id]
        $apiResources['your_resources'] = array(
            // Module associated with your resource.
            'module' => 'your-plugin-name', 
            // Controller associated with your resource.
            'controller' => 'your-resource-controller',
            // Type of record associated with your resource.
            'record_type' => 'YourResourceRecord',
            // List of actions available for your resource.
            'actions' => array(
                'index',  // GET request without ID
                'get',    // GET request with ID
                'post',   // POST request
                'put',    // PUT request (ID is required)
                'delete', // DELETE request (ID is required)
            ), 
            // List of GET parameters available for your index action.
            'index_params' => array('foo', 'bar'), 
        );
        return $apiResources;
    }

If not given, ``module`` and ``controller`` fall back to their defaults,
"default" and "api". Resources using the default controller MUST include
a ``record_type``. Remove ``actions`` that are not wanted or not
implemented. For index actions, all GET parameters must be registered
with the ``index_params`` whitelist.

Using the Default Controller
----------------------------

If your resource corresponds to an Omeka record, we highly recommend
that you use the default controller. Doing so will ensure consistent
behavior across resources. These records must extend
``Omeka_Record_AbstractRecord``, implement
``Zend_Acl_Resource_Interface``, and have a corresponding API adapter
called ``Api_{YourRecordType}`` that must extend
``Omeka_Record_Api_AbstractRecordAdapter`` and be saved to your plugin's
models directory in a subdirectory named Api. This adapter is
responsible for building representations of, and setting properties to,
your record.

For example, an API adapter for ``YourRecordType`` saved to
YourPlugin/models/Api/YourRecordType.php:

.. code-block:: php

    <?php
    class Api_YourRecordType extends Omeka_Record_Api_AbstractRecordAdapter
    {
        // Get the REST representation of a record.
        public function getRepresentation(Omeka_Record_AbstractRecord $record)
        {
            // Return a PHP array, representing the passed record.
        }
        
        // Set data to a record during a POST request.
        public function setPostData(Omeka_Record_AbstractRecord $record, $data)
        {
            // Set properties directly to a new record.
        }
        
        // Set data to a record during a PUT request.
        public function setPutData(Omeka_Record_AbstractRecord $record, $data)
        {
            // Set properties directly to an existing record.
        }
    }

``Omeka_Record_Api_AbstractRecordAdapter`` provides a few convenience
methods that make representation and record building easier:

-  ``getResourceUrl($uri)``: Get the absolute URL to the passed
   resource. The convention is to provide an absolute URL to all
   resources in your representations, identified by the "url" key. This
   follows a hypermedia approach to API design, offering the client an
   easy way to consume and locate available resources. Note that this is
   a static method, which means you can use it in your plugin class when
   extending an existing resource (see "Extending Existing Resources"
   below).
-  ``getDate($date)``: Format a date string as an ISO 8601 date, UTC
   timezone. The convention is to convert all dates to this format. Note
   that this is a static method.
-  ``getElementTextRepresentations($record)``: Get representations of
   element texts belonging to a record. The record must initialize the
   ElementText mixin.
-  ``setElementTextData($record, $data)``: Set element text data to a
   record. The record must initialize the ElementText mixin.

By implementing ``Zend_Acl_Resource_Interface``, you record class must
include the ``getResourceId()`` method. This identifies your record as
relating to a unique ACL resource ID, which is used during permission
checks, often automatically.

.. code-block:: php

    <?php
    public function getResourceId()
    {
        // This is typically the name of the plugin, an underscore, and the pluralized record type.
        return 'YourPlugin_YourRecords';
    }

You may find this resource ID already defined in the plugin's
``define_acl`` hook. If not you'll need to add it yourself:

.. code-block:: php

    <?php
    public function hookDefineAcl($args)
    {
        $acl = $args['acl'];
        $acl->addResource('YourPlugin_YourRecords');
    }

One last thing you may need to do is filter the select object in the
record's table class by overriding ``Omeka_Db_Table::getSelect()``. This
should protect unauthorized API users from viewing non-public records:

.. code-block:: php

    <?php
    public function getSelect()
    {
        $select = parent::getSelect();
        $permissions = new Omeka_Db_Select_PublicPermissions('YourPlugin_YourRecords');
        // Where "your_records" is the table alias, "owner_column" is the user column to check against, 
        // and "public_column" is the permissions column to check against.
        $permissions->apply($select, 'your_records', 'owner_column', 'public_column');
        return $select;
    }

Extending Existing Resources
----------------------------

You can extend the representations of existing resources by using the
``api_extend_*`` filter, where \* is the resource you want to extend.

.. code-block:: php

    <?php
    protected $_filters = array('api_extend_items');

    public function filterApiExtendItems($extend, $args)
    {
        $item = $args['record'];
        
        // For one resource:
        $resourceId = $this->_db->getTable('YourResource')->findByItemId($item->id);
        $extend['your_resources'] = array(
            'id' => 1,
            'url' => Omeka_Record_Api_AbstractRecordAdapter::getResourceUrl("/your_resources/{$resourceId->id}"),
            'resource' => 'your_resources',
        );
        
        // Or, for multiple resources:
        $extend['your_resources'] = array(
            'count' => 10,
            'url' => Omeka_Record_Api_AbstractRecordAdapter::getResourceUrl("/your_resources?item={$item->id}"),
            'resource' => 'your_resources',
        );
        
        return $extend;
    }

Note that the API enforces a pattern when extending a resource:

-  ``id`` and ``url`` for a one-to-one relationship
-  ``count`` and ``url`` for a one-to-many relationship
-  ``resource`` is recommeded but not required

All other keys pass through as custom data that may be used for the client's 
convenience.
