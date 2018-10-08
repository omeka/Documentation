################################
Representative Files for Records
################################

.. versionadded:: 2.2

Traditionally in Omeka, only Files and Items could easily be represented by
graphics like thumbnails. Files can be displayed with :php:func:`file_markup`
or as thumbnails with :php:func:`file_image`, and Items could use
:php:func:`files_for_item` to show all their files, or
:php:func:`item_image` to show the thumbnail of their first attached File.

Omeka 2.2 allows records other than Items to show thumbnails and other
functionality that depends on File records by choosing a "representative"
file. Omeka uses this functionality in the views for some records like
Collections and Files, and also in the search results page.

Themes and plugins can use a new helper function to display thumbnails for
records with representative files, and plugins can also select and expose
representatives for their own records.

******************************
Showing thumbnails for records
******************************

Instead of the existing functions which are different for every type of record
that can have a thumbnail, the new representative file system has just one
helper function: :php:func:`record_image`. ``record_image`` works just like
``file_image`` or ``item_image``, but it will work for any type of record
that has a representative file.

So, a theme can use this same function across the views for any number of
record types, and can even use it on views where multiple different record
types may appear.

To directly use the existing functions that work on Files, you can also call
the :php:meth:`Omeka_Record_AbstractRecord::getFile` method on the record,
which will return the File object for the representative file. You can pass
that File to helpers like :php:func:`file_markup`.

********************************************
Using representative files in plugin records
********************************************

Plugins can also add representative file support to their own records. These
records will then work with :php:func:`record_image`, so the plugin's views
can use that function to show thumbnails. Thumbnails will also show when those
records appear in search results and any other places already using ``record_image``.

To have a representative files for its instances, a Record subclass must override
:php:meth:`Omeka_Record_AbstractRecord::getFile`. ``getFile`` takes no arguments,
and the record simply has to return a File object from it. Records can use any
strategy they want to select a representative file.

For example, Omeka's own records use a variety of strategies:

* Files return ``$this``, since they "represent" themselves
* Items return their first attached File
* Collections select an item in the collection, preferring featured items, and return
  that item's first File
* Exhibits return the attached File that appears earliest in the exhibit
