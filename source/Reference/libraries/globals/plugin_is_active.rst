.. _fpluginisactive:

############################################################################
``plugin_is_active`` — Determine whether a plugin is installed and active.
############################################################################

:doc:`Plugin-related functions </Reference/packages/Function/Plugin/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/plugin_is_active.rst

.. php:function:: plugin_is_active($name, $version = null, $compOperator = '>=')

    Determine whether a plugin is installed and active.
    
    May be used by theme/plugin writers to customize behavior based on the
    existence of certain plugins. Some examples of how to use this function:
    
    Check if ExhibitBuilder is installed and activated.
    <code>
    if (plugin_is_active('ExhibitBuilder')):
    </code>
    
    Check if installed version of ExhibitBuilder is at least version 1.0 or
    higher.
    <code>
    if (plugin_is_active('ExhibitBuilder', '1.0')):
    </code>
    
    Check if installed version of ExhibitBuilder is anything less than 2.0.
    <code>
    if (plugin_is_active('ExhibitBuilder', '2.0', '<')):
    </code>
    
    :type $name: string
    :param $name: Directory name of the plugin.
    :type $version: string
    :param $version: Version of the plugin to check.
    :type $compOperator: string
    :param $compOperator: Comparison operator to use when checking the installed version of ExhibitBuilder.
    :returns: boolean

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/plugin_is_active.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/plugin_is_active.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/plugin_is_active.rst

