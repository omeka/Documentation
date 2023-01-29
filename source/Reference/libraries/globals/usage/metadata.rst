------
Record
------

The first parameter can be either a record object or the string name of a
record type. The string form is used when accessing "current" records set
through :php:func:`set_current_record` or :php:func:`loop`.

--------
Metadata
--------

For records that carry Element Set metadata, get the value for an element by
passing the element set and element name as an array in the second parameter,
e.g. ``array('Dublin Core', 'Title')``.

You can also get properties of the record by passing the name of the property as
a string in the second parameter. Valid property names differ between record
types. Every public property of a record (sometimes called the "columns"
of the record because this is the data stored in the columns of the database) is
a valid metadata name here. Many records have special additional properties that
are available as well:

* Collection

  * ``total_items``

  * ``display_title``

  * ``rich_title``

* File

  * ``uri``

  * ``fullsize_uri``

  * ``thumbnail_uri``

  * ``square_thumbnail_uri``

  * ``permalink``

  * ``display_title``

  * ``rich_title``

* Item

  * ``item_type_name``

  * ``collection_name``

  * ``permalink``

  * ``has_files``

  * ``file_count``

  * ``has_thumbnail``

  * ``citation``

  * ``display_title``

  * ``rich_title``

Since version 2.5, all the Element Set-carrying records (Collection, File and Item)
have the special property ``display_title`` that returns a simplified version of their
title without any HTML tags.

Since version 2.8, the same records also have a special property ``rich_title`` that
preserves only simple inline formatting HTML tags in the title (``em``, ``strong``,
``i``, ``b``, and ``u``), suitable for use when printing a title within HTML and allowing
some formatting while avoiding interference with any wrapping markup around the title like
links or headings.

The above list only covers core records. For other records, like those added by plugins,
see the plugin's documentation or the ``getProperty()`` method of the record.

-------
Options
-------

Valid keys for the ``$options`` array are:
 
* ``all``: If true, return an array containing all values for the field.
 
* ``delimiter``: Return the entire set of metadata as a string, where entries are separated by the given delimiter.
 
* ``index``: Return the metadata entry at the given zero-based index.
 
* ``no_escape``: If true, do not escape the resulting values for HTML entities.
 
* ``no_filter``: If true, return the set of metadata without running any :doc:`filters </Tutorials/understandingFilters>`. 
 
* ``snippet``: Trim the length of each piece of text to the given length in characters.

* ``ignore_unknown``: If true, do not throw an error if the requested metadata element does not exist. (Since version 2.5)

* Passing simply the string 'all' is equivalent to ``array('all' => true)``
 
* Passing simply an integer is equivalent to ``array('index' => [the integer])``
