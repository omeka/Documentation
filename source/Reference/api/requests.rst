########
Requests
########

Endpoint URL
------------

::

    yourdomain.com/api/

Pagination
----------

| For index requests using the defualt controller, pagination is set in
the response's ``Link`` header:
| ``header Link: <http://yourdomain.com/api/items?page=1&per_page=50>; rel="first",        <http://localhost/omeka/api/items?page=10&per_page=50>; rel="last",        <http://localhost/omeka/api/items?page=1&per_page=50>; rel="previous",        <http://localhost/omeka/api/items?page=3&per_page=50>; rel="next"``

Global GET Parameters
---------------------

-  **key**: string, API key authentication
-  **callback**: string, JSONP function name
-  **pretty\_print**: on/off, Pretty print the JSON output

Generic Requests
----------------

``POST`` and ``PUT`` requests are designed to take a JSON payload that
is essentially identical to a ``GET`` response of the same resource.
This makes it possible to, for example, ``GET`` an item, modify the
representation directly and ``POST`` or ``PUT`` it back to Omeka.

GET a resource
~~~~~~~~~~~~~~

| Return data about the specified resource (most often a specific
record):
| ``GET /:resources/:id``

GET one or more resources
~~~~~~~~~~~~~~~~~~~~~~~~~

| Return data about resources (most often records):
| ``GET /:resources``
| \* **page**: integer

A response of a resource using the default controller will include a
non-standard ``Omeka-Total-Results`` header set to the total count of
request results.

POST a resource
~~~~~~~~~~~~~~~

| Create a new resource:
| ``POST /:resources``

PUT a resource
~~~~~~~~~~~~~~

| Update an existing resource:
| ``PUT /:resource/:id``

DELETE a resource
~~~~~~~~~~~~~~~~~

| Delete a resource
| ``DELETE /:resource/:id``

Errors
------

Router Errors
~~~~~~~~~~~~~

All requests may return the following errors:

-  ``400 Bad Request``
-  Invalid GET request parameter: "[parameter]"
-  ``403 Forbidden``
-  Invalid key.
-  API is disabled
-  ``404 Not Found``
-  The "[resource]" resource is unavailable.
-  ``405 Method Not Allowed``
-  This resource does not implement the "[action]" action.
-  POST requests must not include an ID.
-  PUT and DELETE requests must include an ID.
-  ``500 Internal Server Error``
-  Resources using the default controller must register a record type.

Default Controller Errors
~~~~~~~~~~~~~~~~~~~~~~~~~

Requests to the default controller may return the following errors:

-  ``400 Bad Request``
-  Invalid request. Request body must be a JSON object.
-  Error when saving record.
-  ``403 Forbidden``
-  Permission denied.
-  ``404 Not Found``
-  Invalid record. Record not found.
-  Invalid record. Record type "[record\_type]" not found.
-  Invalid record adapter. Record adapter "[record\_adapter\_class]" not
   found.
-  ``500 Internal Server Error``
-  Invalid record adapter. Record adapter "[record\_adapter\_class]" is
   invalid
-  Invalid record. Record "[record\_type]" must define an ACL resource.

Record Errors
~~~~~~~~~~~~~

Requests that invoke the abstract record adapter may return the
following errors:

-  ``500 Internal Server Error``
-  The "[record\_type]" API record adapter does not implement
   setPostData
-  The "[record\_type]" API record adapter does not implement setPutData
