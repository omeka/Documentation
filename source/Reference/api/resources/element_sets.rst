############
Element Sets
############

GET element set
---------------

Return data about the specified element set:

Request
~~~~~~~

::

    GET /element_sets/:id

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

::

    GET /element_sets

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

::

    POST /element_sets

.. code-block:: json

    {
      "name": "Dublin Core",
      "description": "The Dublin Core metadata element set is common to all Omeka records."
    }

Response
~~~~~~~~

.. code-block:: header

    Location: http://yourdomain.com/api/element_sets/:id

An JSON representation of the newly created element set (see above).

PUT element set
---------------

Edit an existing element set.

Request
~~~~~~~

::

    PUT /element_sets/:id

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

::

    DELETE /element_sets/:id

Response
~~~~~~~~

An ``204 No Content`` response.
