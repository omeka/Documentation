The ``metadata`` function is the easiest and safest way to include record
metadata in HTML output. ``metadata`` offers support for Element Text
metadata, data stored directly in database columns, and custom metadata
properties.

``metadata`` automatically returns output HTML-escaped for inclusion in
a page where appropriate. The escaping can be optionally disabled. Values
also automatically passed through the
:doc:`/Reference/filters/Element_Display_Filter`, though this too can be
optionall disabled.
