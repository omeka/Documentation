###########
Collections
###########

GET collection
--------------

Return data about the specified collection.

Request
~~~~~~~

.. code-block:: http

    GET /collections/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: json

    {
      "id": 1,
      "url": "http://yourdomain.com/api/collections/1",
      "public": true,
      "featured": false,
      "added": "2013-03-27T08:17:37+00:00",
      "modified": "2013-04-21T15:05:07+00:00", 
      "owner": {"id": 1, "url": "/users/1"},
      "items": {"count": 100, "url": "http://yourdomain.com/api/items?collection=1"},
      "element_texts": [
        {
          "html": false,
          "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          "element_set": {"id": 1, "url": "http://yourdomain.com/api/element_sets/1", "name": "Dublin Core"},
          "element": {"id": 1, "url": "http://yourdomain.com/api/elements/1", "name": "Title"}
        }
      ]
    }

GET collections
---------------

Return data about collections.

Request
~~~~~~~

.. code-block:: http

    GET /collections HTTP/1.1

Parameters
^^^^^^^^^^

-  **public**: boolean
-  **featured**: boolean
-  **added\_since**: string (ISO 8601)
-  **modified\_since**: string (ISO 8601)
-  **owner** (user): integer

Response
~~~~~~~~

An array of JSON collection representations (see above).

POST collection
---------------

Create a new collection.

Request
~~~~~~~

.. code-block:: http

    POST /collections HTTP/1.1

.. code-block:: json

    {
      "public": true,
      "featured": false,
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
    Location: http://yourdomain.com/api/collections/:id

An JSON representation of the newly created collection (see above).

PUT collection
--------------

Edit an existing collection.

Request
~~~~~~~

.. code-block:: http

    PUT /collections/:id HTTP/1.1

.. code-block:: json

    {
      "public": true,
      "featured": false,
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

An JSON representation of the newly edited collection (see above).

DELETE collection
-----------------

Delete a collection.

Request
~~~~~~~

.. code-block:: http

    DELETE /collections/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 204 No Content
