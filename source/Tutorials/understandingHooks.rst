###################
Understanding Hooks
###################

Hooks and :doc:`Filters <understandingFilters>` are the two ways to modify and extend Omeka's capabilities. A hook "fires" in response to some action taking place in Omeka, such as saving a record, deleting a record, rendering some kinds of pages, installing a plugin, etc.

When a hook fires, it sends relevant data to a callback function. The callback function then performs any necessary actions with the data before Omeka moves on to the next callback registered for the hook, or if no more callback remain Omeka continues on with its own processing.

To take a common example, plugins will often add new kinds of information about items in Omeka. Thus, when items are saved, various plugins will need to update their own records to reflect the new changes. Since Omeka itself knows nothing of the extended functionality, this takes place through the :doc:`before_save_item </Reference/hooks/before_save_<model>>` and :doc:`after_save_item </Reference/hooks/after_save_<model>>` hooks.

Those callbacks to those hooks get data about the record and about the ``$_POST`` data submitted. The callbacks define by each plugin run in turn, updating their own records. After all of the callbacks have run, Omeka finally completes its process for saving the item.

Another common example is the :doc:`/Reference/hooks/install` hook. This fires when a plugin is activated, so unlike the previous example only one callback is run -- the callback defined by that plugin. This is where a plugin would create its database tables, set options, and do any other initial setup.


Hook callbacks always receive one array of arguments (though that array may be empty). They never return a value. If content is to be printed to the screen, they should use ``echo`` internally.  
