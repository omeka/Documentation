############
Element Sets
############

GET element set
---------------

Return data about the specified element set:

Request
~~~~~~~

.. code-block:: http

    GET /element_sets/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: json

    {
      "id": 1,
      "url": "http://yourdomain.com/api/element_sets/1",
      "record_type": null,
      "name": "Dublin Core",
      "description": "The Dublin Core metadata element set is common to all Omeka records.",
      "elements": {"count": 100, "url": "http://yourdomain.com/api/elements?element_set=1"}
    }

GET element sets
----------------

Return data about element sets:

Request
~~~~~~~

.. code-block:: http

    GET /element_sets HTTP/1.1

Parameters
^^^^^^^^^^

-  **name**: string
-  **record\_type**: string

Response
~~~~~~~~

An array of JSON element set representations (see above).

POST element set
----------------

Create a new element set.

Request
~~~~~~~

.. code-block:: http

    POST /element_sets HTTP/1.1

.. code-block:: json

    {
      "name": "Dublin Core",
      "description": "The Dublin Core metadata element set is common to all Omeka records."
    }

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 201 Created
    Location: http://yourdomain.com/api/element_sets/:id

An JSON representation of the newly created element set (see above).

PUT element set
---------------

Edit an existing element set.

Request
~~~~~~~

.. code-block:: http

    PUT /element_sets/:id HTTP/1.1

.. code-block:: json

    {
      "name": "Dublin Core",
      "description": "The Dublin Core metadata element set is common to all Omeka records."
    }

Response
~~~~~~~~

An JSON representation of the newly edited element set (see above).

DELETE element set
------------------

Delete an element set. "Dublin Core" and "Item Type Metadata" element
sets may not be deleted.

Request
~~~~~~~

.. code-block:: http

    DELETE /element_sets/:id

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 204 No Content
