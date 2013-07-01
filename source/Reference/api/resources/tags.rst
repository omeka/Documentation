####
Tags
####

GET tag
-------

Return data about the specified tag.

Request
~~~~~~~

::

    GET /tag

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

::

    GET /tags

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

::

    DELETE /tags/:id

Response
~~~~~~~~

An ``204 No Content`` response.
