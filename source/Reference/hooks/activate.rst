########
activate
########

.. versionadded:: 2.1

*****
Usage
*****

The activate hook is fired whenever a plugin is activated. Most things plugins do
will automatically be handled by normal deactivation, but a plugin could use this
hook along with :doc:`deactivate` to manage changes it has made external to the
plugin that should be enabled and disabled.

For most use cases, plugins should be using :doc:`install` or :doc:`initialize`
instead of this hook.

*********
Arguments
*********

This hook has no arguments.

********
Examples
********

