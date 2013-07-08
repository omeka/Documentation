#####
Items
#####

GET item
--------

Return data about the specified item.

Request
~~~~~~~

.. code-block:: http

    GET /items/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: json

    {
      "id": 1,
      "url": "http://yourdomain.com/api/items/1",
      "item_type": {
        "id": 1, 
        "url": "http://yourdomain.com/api/item_types/1", 
        "name": "Text", 
        "resource": "item_types"
      },
      "collection": {
        "id": 1, 
        "url": "http://yourdomain.com/api/collections/1", 
        "resource": "collections"
      },
      "owner": {
        "id": 1, 
        "url": "http://yourdomain.com/api/users/1", 
        "resource": "users"
      },
      "public": true,
      "featured": false,
      "added": "2013-03-27T08:17:37+00:00",
      "modified": "2013-04-21T15:05:07+00:00", 
      "files": {
        "count": 100, 
        "url": "http://yourdomain.com/api/files?item=1", 
        "resource": "files"
      },
      "tags": [
        {
          "id": 1, 
          "url": "http://yourdomain.com/api/tags/1", 
          "name": "foo", 
          "resource": "tags"
        }
      ],
      "element_texts": [
        {
          "html": false,
          "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          "element_set": {
            "id": 1, 
            "url": "http://yourdomain.com/api/element_sets/1", 
            "name": "Dublin Core", 
            "resource": "element_sets"
          },
          "element": {
            "id": 1, 
            "url": "http://yourdomain.com/api/elements/1", 
            "name": "Title", 
            "resource": "elements"
          }
        }
      ]
    }

GET items
---------

Return data about items.

Request
~~~~~~~

.. code-block:: http

    GET /items HTTP/1.1

Parameters
^^^^^^^^^^

-  **collection**: integer
-  **item\_type**: integer
-  **featured**: boolean
-  **public**: boolean
-  **added\_since**: string (ISO 8601)
-  **modified\_since**: string (ISO 8601)
-  **owner** (user): integer

Response
~~~~~~~~

An array of JSON item representations (see above).

POST item
---------

Create a new item.

Request
~~~~~~~

.. code-block:: http

    POST /items HTTP/1.1

.. code-block:: json

    {
      "item_type": {"id": 1},
      "collection": {"id": 1},
      "public": true,
      "featured": false,
      "tags": [
        {"name": "foo"},
        {"name": "bar"} 
      ],
      "element_texts": [
        {
          "html": false,
          "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          "element": {"id": 1}
        }
      ]
    }

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 201 Created
    Location: http://yourdomain.com/api/items/:id

An JSON representation of the newly created item (see above).

PUT item
--------

Edit an existing item.

Request
~~~~~~~

.. code-block:: http

    PUT /items/:id HTTP/1.1

.. code-block:: json

    {
      "item_type": {"id": 1},
      "collection": {"id": 1},
      "public": true,
      "featured": false,
      "tags": [
        {"name": "foo"},
        {"name": "bar"} 
      ],
      "element_texts": [
        {
          "html": false,
          "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          "element": {"id": 1}
        }
      ]
    }

Response
~~~~~~~~

An JSON representation of the newly edited item (see above).

DELETE item
-----------

Delete an item.

Request
~~~~~~~

.. code-block:: http

    DELETE /items/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 204 No Content
