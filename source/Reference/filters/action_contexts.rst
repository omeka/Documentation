.. _actioncontexts:

###############
action_contexts
###############

*****
Usage
*****

Action contexts work in combination with :doc:`response_contexts` to output additiona formats, such as RSS or JSON.

Typically, you check whether the controller passed in the arguments is one defined by your plugin, then add your context (output format) to the array of values.

Then, response contexts you define direct Omeka to the views you have defined for the output.

*****
Value
*****

``array`` $contexts
    Array of the contexts available for a controller's views.

*********
Arguments
*********

:php:class:`Omeka_Controller_Action` controller
    The controller that is producing the output.
    
`Zend_Controller_ActionHelper_ContextSwitch <http://framework.zend.com/manual/1.12/en/zend.controller.actionhelpers.html#zend.controller.actionhelpers.contextswitch> context_switch
        

********
Examples
********

Make an RSS feed of your records available at ``/my-records/browse?output=rss``

.. code-block:: php

    class MyRecordController extends Omeka_Controller_AbstractActionController
    {
        //nothing to do here, since we don't need to override anything
    }

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = array('action_contexts');
    
        public filterActionContexts($contexts, $args)
        {
            if($args['controller'] instanceof MyRecordController) {
                $contexts['browse'][] = 'rss'; 
            }        
            return $contexts;
        }
    }
    
********
See Also
********

:doc:`response_contexts`    
