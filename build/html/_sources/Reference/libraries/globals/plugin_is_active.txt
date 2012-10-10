################
plugin_is_active
################

*******
Summary
*******

.. include:: summary/plugin_is_active.rst

.. php:function:: plugin_is_active($name, $version, $compOperator = >=)

    Determine whether a plugin is installed and active.
    
    May be used by theme/plugin writers to customize behavior based on the existence of certain plugins. Some examples
    of how to use this function:
    
    Check if ExhibitBuilder is installed and activated.	               
    
    .. code-block:: php 
    
    
    	                   if (plugin_is_active('ExhibitBuilder')):
    
    
    Check if installed version of ExhibitBuilder is at least version 1.0 orhigher.	               
    
    .. code-block:: php 
    
    
    	                   if (plugin_is_active('ExhibitBuilder', '1.0')):
    
    
    Check if installed version of ExhibitBuilder is anything less than 2.0.	               
    
    .. code-block:: php 
    
    
    	                   if (plugin_is_active('ExhibitBuilder', '2.0', '<')):
    
    :param unknown $name: 
    :param unknown $version: 
    :param unknown $compOperator:

*****
Usage
*****

.. include:: usage/plugin_is_active.rst

********
Examples
********

.. include:: examples/plugin_is_active.rst

********
See Also
********

.. include:: see_also/plugin_is_active.rst

