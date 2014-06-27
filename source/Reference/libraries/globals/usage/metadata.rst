The first parameter can be either a record or the name of the current record type. The latter usage is helpful when
looping through records.

For records that carry Element Set metadata, get the value for an element by passing the element set and element name
as an array in the second parameter, e.g. ``array('Dublin Core', 'Title')``

You can also get properties of the record by passing the name of the property as a string in the second parameter.

Valid keys for the ``$options`` array are:
 
* ``all``: If true, return an array containing all values for the field.
 
* ``delimiter``: Return the entire set of metadata as a string, where entries are separated by the given delimiter.
 
* ``index``: Return the metadata entry at the given zero-based index.
 
* ``no_escape``: If true, do not escape the resulting values for HTML entities.
 
* ``no_filter``: If true, return the set of metadata without running any :doc:`filters </Tutorials/understandingFilters>`. 
 
* ``snippet``: Trim the length of each piece of text to the given length in characters.
 
* Passing simply the string 'all' is equivalent to ``array('all' => true)``
 
* Passing simply an integer is equivalent to ``array('index' => [the integer])``
