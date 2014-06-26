---------------
Output_ItemAtom
---------------

Package: :doc:`Output </Reference/packages/Output/index>`

.. php:class:: Output_ItemAtom

    Model class for an Atom feed for a list of items.

    .. php:method:: __construct($items)

        Build the Atom feed using DOM.

        :type $items: array
        :param $items: An array of Item records.
        :returns: void

    .. php:method:: _getFeedLinks($items)

        Returns the URLs, if any, for rel=self|next|previous links.

        :type $items: array
        :param $items:
        :returns: array

    .. php:method:: getFeed()

        Returns the XML feed.

        :returns: string
