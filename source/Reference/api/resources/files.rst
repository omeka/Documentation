#####
Files
#####

GET file
--------

Return data about the specified file.

Request
~~~~~~~

.. code-block:: http

    GET /files/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: json

    {
      "id": 1,
      "url": "/files/1",
      "file_urls": {
        "original": "http://yourdomain.com/files/original/2b42672de6e47a67698a52e1415bd2c0.pdf",
        "fullsize": "http://yourdomain.com/files/fullsize/2b42672de6e47a67698a52e1415bd2c0.jpg",
        "thumbnail": "http://yourdomain.com/files/thumbnails/2b42672de6e47a67698a52e1415bd2c0.jpg",
        "square_thumbnail": "http://yourdomain.com/files/square_thumbnails/2b42672de6e47a67698a52e1415bd2c0.jpg"
      },
      "item": {
        "id": 1, 
        "url": "http://yourdomain.com/api/items/1", 
        "resource": "items"
      },
      "order": null,
      "size": 1953540,
      "has_derivative_images": true,
      "authentication": "f6089bca39470e8c19410242061b1f78",
      "mime_type": "audio/mpeg",
      "type_os": "MPEG ADTS, v1, 128 kbps, 44.1 kHz, JntStereo",
      "filename": "54a21c1552feef92069d504fbaf145a8.mp3",
      "original_filename": "1ATwUDzA3SCU.128.mp3",
      "added": "2013-03-27T08:17:37+00:00",
      "modified": "2013-04-21T15:05:07+00:00", 
      "stored": true,
      "metadata": {},
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

Note on "metadata"
~~~~~~~~~~~~~~~~~~

The ``metadata`` object contains data extracted by the `getId3
library <http://getid3.sourceforge.net/>`__, and so its structure and
content will vary widely based on the file type, what data the library
is able to extract, and what data is embedded in the file.

Possible properties within ``metadata`` (if it is not empty) are:
mime\_type, video, audio, comments, comments\_html, iptc, jpg.
``mime_type`` within ``metadata`` is a string, and can differ from the
``mime_type`` property in the top level of the response. All other
properties will be objects.

GET files
---------

Return data about files.

Request
~~~~~~~

.. code-block:: http

    GET /files HTTP/1.1

Parameters
^^^^^^^^^^

-  **item**: integer
-  **order**: integer
-  **size\_greater\_than**: integer
-  **has\_derivative\_image**: boolean
-  **mime\_type**: string
-  **added\_since**: string (ISO 8601)
-  **modified\_since**: string (ISO 8601)

Response
~~~~~~~~

An array of JSON file representations (see above).

POST files
----------

Create a new file. Only one file may be uploaded at a time.

Request
~~~~~~~

.. code-block:: http

    POST /files HTTP/1.1

Requests must use the
```multipart/form-data`` <http://www.w3.org/TR/html401/interact/forms.html#h-17.13.4.2>`__
content type. The content disposition name for the file must be
``file``. The content disposition name for the JSON data must be
``data``. We highly recommend that you use a HTTP client that is capable
of encoding form-data requests for you, but the typical request should
look something like this:

.. code-block:: http

    POST /api/files HTTP/1.1
    Content-Type: multipart/form-data; boundary=E19zNvXGzXaLvS5C

    ----E19zNvXGzXaLvS5C
    Content-Disposition: form-data; name="data"

    {
      "order": 2,
      "item": {
        "id": 1,
      }
      "element_texts": [
        {
          "html": false,
          "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          "element": {"id": 1}
        }
      ]
    }
    ----E19zNvXGzXaLvS5C
    Content-Disposition: form-data; name="file"; filename="example.pdf"
    Content-Type: application/pdf

    ...contents of example.pdf...
    ----E19zNvXGzXaLvS5C

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 201 Created
    Location: http://yourdomain.com/api/files/:id

An JSON representation of the newly created file (see above).

PUT file
--------

Edit an existing file.

Request
~~~~~~~

.. code-block:: http

    PUT /files/:id HTTP/1.1

.. code-block:: json

    {
      "order": 2,
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

An JSON representation of the newly edited file (see above).

DELETE file
-----------

Delete a file.

Request
~~~~~~~

.. code-block:: http

    DELETE /files/:id HTTP/1.1

Response
~~~~~~~~

.. code-block:: http

    HTTP/1.1 204 No Content

Errors
------

In addition to the general errors, requests to the files resource may
return the following errors:

-  ``400 Bad Request``

   -  Invalid request. Request body must be a JSON object.
   -  Invalid request. Exactly one file must be uploaded per request.
   -  Invalid request. Missing JSON data.
   -  Invalid item. File must belong to an existing item.

-  ``500 Internal Server Error``

   -  Invalid request. The default job dispatcher must be synchronous.
