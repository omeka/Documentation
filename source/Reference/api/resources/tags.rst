####
Tags
####

GET tag
-------

Return data about the specified tag.

Request
~~~~~~~

.. code-block:: http

    GET /tag HTTP/1.1

Response
~~~~~~~~

.. code-block:: json

    {
      "id": 1,
      "url": "http://yourdomain.com/api/tags/1",
      "name": "foo"
    }

GET tags
--------

Return data about tags.

Request
~~~~~~~

.. code-block:: http

    GET /tags HTTP/1.1

Response
~~~~~~~~

An array of JSON tag representations (see above).

POST tag
--------

New tags must be created via the owner record.

DELETE tag
----------

Delete a tag.

Request
~~~~~~~

.. code-block:: http

    DELETE /tags/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 204 No Content
