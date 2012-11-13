
The first parameter can be either a record or the name of the current record type. The latter usage is helpful when looping through records.

For records that carry Element Set metadata, get the value for an element by passing the element set and element name as an array in the second parameter, e.g. ``array('Dublin Core', 'Title')``

You can also get properties of the record by passing the name of the property as a string in the second parameter.