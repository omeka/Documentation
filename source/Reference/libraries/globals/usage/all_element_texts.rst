Valid keys for the ``$options`` array are:
 
* ``show_empty_elements``: Whether to include elements that have no values. If specified, this
  overrides the corresponding site setting. If a string is passed, empty elements will be
  displayed and the string will be used as the replacement text shown for the empty elements.

* ``show_element_set_headings``: Whether to show the headings naming each element set
  (e.g., "Dublin Core"). If specified this overrides the corresponding site setting.

* ``show_element_sets``: Array of names of element sets to show. If omitted, all sets are
  included (except totally empty sets when ``show_empty_elements`` is false).
 
* ``return_type``: What kind of output the function should return. Must be one of ``"html"``
  or ``"array"``. HTML output is the default, and the usual use case. Array output, when
  selected here, returns the text data indexed by element set and element.
 
* ``partial``: Path to the view partial script used to create the HTML output. By default
  the path is ``'common/record-metadata.php'``.
