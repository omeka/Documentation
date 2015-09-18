#####################
Understanding Filters
#####################

:doc:`Hooks <understandingHooks>` and filters are the two ways to modify
and extend Omeka's capabilities. Filters are a way for data in Omeka to be
passed among different plugins that want to add to it or modify it in some
way before final processing by Omeka. Typical examples include adding
navigation links and changing default behaviors.


*************
Filter Basics
*************

Filters work similarly to hooks, but are focused on modifying data rather
than simply executing code or producing output in some particular place.
Filter functions always recieve two parameters.

The first parameter is always the value being filtered. The documentation
page for a filter will describe this parameter under the heading "Value."
A filter function is expected to take the value passed in that parameter,
modify it somehow (though this can include completely replacing it or
leaving it unchanged), and return the result. That returned value is what's
passed to any later functions attached to the same filter, and eventually
back to the code that applied the filter in the first place. Since filters
work this way, there's aclear distinction from how hooks work in this case:
filter functions filter functions  **must** return a value.

The second parameter to a filter function is conventionally called ``$args``.
Just like with hooks, ``$args`` is an array of arguments, optional useful
pieces of extra data passed along with the hook to provide context or
access to objects that might likely be needed by the filter function. The
arguments passed with a filter are documented under the heading "Arguments."

************************
Using Filters in Plugins
************************

There are two basic ways plugins can use filters, and both work fairly
similarly to hooks: the plugin defines a function and attaches it to the
filter being used.

=================================
Using Omeka_Plugin_AbstractPlugin
=================================

The usual and current way of using filters is to use the features built
into the :doc:`Omeka AbstractPlugin class <understandingOmeka_Plugin_AbstractPlugin>`.
You add the name of the filter you want to use to the ``$_filters`` array
in the plugin class, and then add a public method to the class with the
CamelCased name of the filter and ``filter`` prepended. As an example, to
use the :doc:`/Reference/filters/search_form` filter, the code you would
add would look like this::

    protected $_filters = array(
        'search_form',
    );

    // ...

    public function filterSearchForm($form, $args)
    {
        // Modify or replace $form and return the results
    }

=============================
Using ``add_filter`` directly
=============================

Though the preferred method is to use the AbstractPlugin when using filters
in a plugin, plugins that are built with the old legacy plugin.php-based code or that need to add filters dynamically may need to directly use Omeka's
:php:func:`add_filter` function.

``add_filter`` works very similarly to :php:func:`add_plugin_hook`: you
simply pass it the name of the filter to attach to and the name of a
function you've defined. Using the same ``search_form`` example, the code
for adding a filter this way is pretty similar::

    add_filter('search_form', 'myplugin_search_form');

    function myplugin_search_form($form, $args)
    {
        // Modify or replace $form and return the results
    }

One added wrinkle is that you can also pass in the third argument a
"priority" that determines when your attached function is run relative to
other functions attached to the same filter.
Priority is an integer, and passing a lower priority means your function
will run earlier. For most cases, the default priority setting is fine and
you can simply omit the third argument.
