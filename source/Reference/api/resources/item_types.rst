##########
Item Types
##########

GET item type
-------------

Return data about the specified item type.

Request
~~~~~~~

.. code-block:: http

    GET /item_types/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: json

    {
      "id": 1,
      "url": "/item_types/1",
      "name": "Text",
      "description": "A resource consisting primarily of words for reading.",
      "elements": [
        {"id": 1},
        {"id": 2},
        {"id": 3}
      ],
      "items": {"count": 100, "url": "/items?item_type=1"}
    }

GET item types
--------------

Return data about item types.

Request
~~~~~~~

.. code-block:: http

    GET /item_types HTTP/1.1

Parameters
^^^^^^^^^^

-  **name**: string

Response
~~~~~~~~

An array of JSON item type representations (see above).

POST item type
--------------

Create a new item type.

Request
~~~~~~~

.. code-block:: http

    POST /item_types HTTP/1.1

.. code-block:: json

    {
      "name": "Text",
      "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
      "elements": [
        {"id": 1},
        {"id": 2},
        {"id": 3}
      ]
    }

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 201 Created
    Location: http://yourdomain.com/api/item_types/:id

An JSON representation of the newly created item type (see above).

PUT item type
-------------

Edit an existing item type.

Request
~~~~~~~

.. code-block:: http

    PUT /item_types/:id HTTP/1.1

.. code-block:: json

    {
      "name": "Text",
      "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
      "elements": [
        {"id": 1},
        {"id": 2},
        {"id": 3}
      ]
    }

Response
~~~~~~~~

An JSON representation of the newly edited item type (see above).

DELETE item type
----------------

Delete an item type.

Request
~~~~~~~

.. code-block:: http

    DELETE /item_types/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 204 No Content
