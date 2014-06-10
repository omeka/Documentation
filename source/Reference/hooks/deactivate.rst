##########
deactivate
##########

.. versionadded:: 2.1

*****
Usage
*****

The deactivate hook is fired whenever a plugin is deactivated. Most things plugins do
will automatically be handled by normal deactivation, but a plugin could use this
hook along with :doc:`activate` to manage changes it has made external to the
plugin that should be enabled and disabled.

For most use cases, plugins should be using :doc:`uninstall` instead of this hook, or
simply relying on the fact that its hooks and filters will not run when it is
deactivated.

*********
Arguments
*********

This hook has no arguments.

********
Examples
********

