#########
Resources
#########

GET resource
------------

Individual resources cannot be shown.

GET resources
-------------

Return available API resources and information about them.

Request
~~~~~~~

::

    GET /resources

Response
~~~~~~~~

.. code-block:: json

    {
      "resources": {
        "controller": "resources",
        "actions": ["get"]
      },
      "items": {
        "record_type": "Item",
        "actions": ["index", "get", "post", "put", "delete"],
        "index_params": ["collection", "item_type", "featured", "public", "added_since", "modified_since", "owner"]
      }
    }

POST resource
-------------

Resources cannot be created. They must be registered via the
``api_resources`` filter.
