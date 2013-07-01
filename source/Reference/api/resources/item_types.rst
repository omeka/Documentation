##########
Item Types
##########

GET item type
-------------

Return data about the specified item type.

Request
~~~~~~~

::

    GET /item_types/:id

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

::

    GET /item_types

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

::

    POST /item_types

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

.. code-block:: header

    Location: http://yourdomain.com/api/item_types/:id

An JSON representation of the newly created item type (see above).

PUT item type
-------------

Edit an existing item type.

Request
~~~~~~~

::

    PUT /item_types/:id

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

::

    DELETE /item_types/:id

Response
~~~~~~~~

An ``204 No Content`` response.
