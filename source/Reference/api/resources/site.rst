####
Site
####

GET site
--------

Return information about the Omeka installation.

Request
~~~~~~~

.. code-block:: http

    GET /site HTTP/1.1

Response
~~~~~~~~

.. code-block:: json

    {
      "omeka_url":"http://yourdomain.com",
      "omeka_version":"2.1",
      "title":"My Omeka Site",
      "description":"Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
      "author":"Center for History and New Media",
      "copyright":"Creative Commons Attribution-ShareAlike 3.0 License"
    }
