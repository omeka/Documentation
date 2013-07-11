##################
APIs for beginners
##################

What's a REST API?
~~~~~~~~~~~~~~~~~~

Put simply, an `API <http://en.wikipedia.org/wiki/Api>`__  is a formal 
line of communication between two programs. A 
`REST <http://en.wikipedia.org/wiki/Representational_state_transfer>`__
API is one that utilizes `inherent features of the Web 
<http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol>`__ to
enable communication between a client and a server. It's important to
note that APIs aren't designed to be exposed to you, the end user,
except through intermediary programs. Remember this when you're
experimenting directly with the API; otherwise you may get frustrated.

Omeka's REST API
~~~~~~~~~~~~~~~~

Omeka's REST API provides an *endpoint* against which you can query,
create, update, and delete Omeka *resources*. Your Omeka endpoint is the
URL to your Omeka website followed by ``/api``, like this:

.. raw:: html

   <pre>http://yourdomain.com/api</pre>

You can see which resources are available by appending
``/resources?pretty_print`` to your endpoint, like this:

.. raw:: html

   <pre>http://yourdomain.com/api/resources?pretty_print</pre>

Here you are getting the ``/resources`` resource as a
`JSON <http://en.wikipedia.org/wiki/JSON>`__ object containing all the
available resources and other information about them. (``?pretty_print``
is helpful to get back nicely formatted JSON, but is not necessary.)

HTTP Request Methods
~~~~~~~~~~~~~~~~~~~~

In the above response you'll notice that all resources have at least one
*action*. These actions, while not important to a beginner, correspond
to `HTTP request
methods <http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods>`__.
These methods are central to REST, and you should know what they do:

-  ``GET`` gets one or more representations of a resource;
-  ``POST`` creates a new resource and returns the representation of the
   newly created resource;
-  ``PUT`` modifies an existing resource and returns the representation
   of the newly modified resource;
-  ``DELETE`` deletes an existing resource.

Until you start building your own API client, you won't need to make
``POST``, ``PUT``, or ``DELETE`` requests, but ``GET`` is well suited
for beginners because you can run them directly from your Web browser,
as you probably did above with ``/resources``.

Omeka's Resources and Representations
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A *representation*, in this case, is a JSON object that represents an
Omeka resource. In other words, you are not getting a resource itself,
but rather a representation of it. This is very much like viewing an
item on a Omeka website: the item show page is not the item itself, but
a representation of the item.

Every Omeka website comes with the following resources, most of which
should already be familiar to you as an Omeka user:

-  ``/collections``
-  ``/items``
-  ``/files``
-  ``/item_types``
-  ``/elements``
-  ``/element_sets``
-  ``/tags``

One of the powerful features of the Omeka API is that plugins can add
more resources if they wish. If they do, you'll see them on the
``/resources`` resource.

Using the Omeka API
~~~~~~~~~~~~~~~~~~~

Let's take a look at the ``/items`` resource by making a ``GET`` request
to the following URL using your Web browser:

.. raw:: html

   <pre>http://yourdomain.com/api/items</pre>

Assuming there are already items added to Omeka, you'll see a JSON array
of item representations, each with an "id" (the item ID), a "url" (the
direct URL to that item), and other *metadata* about the item. Copy that
URL to your Web browser and make another ``GET`` request (you'll first
need to remove backslashes from the URL, which were a necessary part of
JSON formatting):

.. raw:: html

   <pre>http://yourdomain.com/api/items/:id</pre>

Where ``:id`` is the item ID. You'll see the same JSON representation of
the item, but by itself. This URL is the item's *canonical* URL, that
is, it is an unambiguous and permanent link that represents the item
itself.

So far you've only been using the ``GET`` method to get representations
of resources. To experiment with ``POST``, ``PUT``, and ``DELETE``
you'll need to use a program that is capable of sending those requests.
Most modern browsers have plugins that do this in a user-friendly way:

-  `Google
   Chrome <https://chrome.google.com/webstore/detail/postman-rest-client/fdmmgilgnpjigdojojpjoooidkmcomcm?hl=en>`__
-  `Mozilla
   Firefox <https://addons.mozilla.org/en-us/firefox/addon/restclient/>`__

If you're comfortable adding, modifying, and deleting Omeka resources,
read the `API documentation <https://omeka.readthedocs.org/en/latest/Reference/api/index.html>`__
and start making requests!
