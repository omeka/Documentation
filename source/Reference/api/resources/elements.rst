########
Elements
########

GET element
-----------

Return data about the specified element:

Request
~~~~~~~

.. code-block:: http

    GET /elements/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: json

    {
      "id": 1,
      "url": "http://yourdomain.com/api/elements/1",
      "name": "Text",
      "order": 1,
      "description": "Any textual data included in the document",
      "comment": null,
      "element_set": {"id": 1, "url": "http://yourdomain.com/api/element_sets/1"},
    }

GET elements
------------

Return data about elements:

Request
~~~~~~~

.. code-block:: http

    GET /elements HTTP/1.1

Parameters
^^^^^^^^^^

-  **element\_set**: integer
-  **name**: string
-  **item\_type**: integer

Response
~~~~~~~~

An array of JSON element representations (see above).

POST element
------------

Create a new element.

Request
~~~~~~~

.. code-block:: http

    POST /elements HTTP/1.1

.. code-block:: json

    {
      "order": 1,
      "name": "Foo",
      "description": "Foo description.",
      "comment": "Foo comment.",
      "element_set": {"id": 1}
    }

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 201 Created
    Location: http://yourdomain.com/api/elements/:id

An JSON representation of the newly created element (see above).

PUT element
-----------

Edit an existing element.

Request
~~~~~~~

.. code-block:: http

    PUT /elements/:id HTTP/1.1

.. code-block:: json

    {
      "order": 1,
      "name": "Foo",
      "description": "Foo description.",
      "comment": "Foo comment.",
      "element_set": {"id": 1}
    }

Response
~~~~~~~~

An JSON representation of the newly edited element (see above).

DELETE element
--------------

Delete an element. Only elements belonging to the "Item Type Metadata"
element set may be deleted.

Request
~~~~~~~

.. code-block:: http

    DELETE /elements/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 204 No Content

Errors
------

In addition to the general errors, requests to the elements resource my
return the following errors:

-  ``400 Bad Request``
-  Invalid record. Only elements belonging to the "Item Type Metadata"
   element set may be deleted.
