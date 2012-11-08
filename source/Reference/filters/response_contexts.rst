.. _responsecontexts:

#################
response_contexts
#################

*****
Usage
*****

Filters the array of response contexts as passed to Zend Framework's ContextSwitch helper.

Response contexts are used to serve the same data (an Item, for example) in different formats. Omeka includes by default response contexts for JSON, RSS and XML response contexts, in addition to the default context, which produces the normal HTML output. 

Suffix values added to the contexts correspond to view files. Thus, to add an RSS feed at url ``my-records/browse?output=rss``, you will have a view named ``browse.rss.php``


*****
Value
*****

``array`` $contexts
    Array of contexts, corresponding to action contexts defined by using :ref:`actioncontexts`

*********
Arguments
*********

None


********
Examples
********

Add an RSS feed at ``my-records/browse?output=rss``

.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = array('define_response_contexts');
        
        public function filterDefineResponseContexts($contexts)
        {
            $contexts['rss'] = array('suffix' => 'rss', 
                                    'headers' => array('Content-Type' => 'text/xml'));
            return $contexts;            
        
        }    
    }
    
