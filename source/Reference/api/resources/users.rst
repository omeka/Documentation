#####
Users
#####

GET user
--------

Return data about the specified user.

Request
~~~~~~~

::

    GET /users/:id

Response
~~~~~~~~

.. code-block:: json

    {
      "id": 1,
      "url": "/users/1",
      "username": "janedoe",
      "name": "Jane Doe",
      "email": "janedoe@example.com",
      "active": true,
      "role": "super"
    }

GET users
---------

Users cannot be browsed.

POST user
---------

Users cannot be created.
