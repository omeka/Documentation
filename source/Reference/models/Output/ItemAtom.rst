---------------
Output_ItemAtom
---------------

.. php:class:: Output_ItemAtom

    Model class for an Atom feed for a list of items.

    .. php:attr:: _feed
    


    .. php:method:: __construct(array $items)
    
        Build the Atom feed using DOM.
        
        :param array $items: An array of Item records.
        :returns: void

    .. php:method:: _getFeedLinks(array $items)
    
        Returns the URLs, if any, for rel=self|next|previous links.
        
        :param array $items: 
        :returns: array

    .. php:method:: getFeed()
    
        Returns the XML feed.
        
        :returns: string

