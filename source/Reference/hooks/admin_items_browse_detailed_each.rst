.. _adminitemsbrowsedetailedeach:

################################
admin_items_browse_detailed_each
################################


*****
Usage
*****

Append content to the details view of an item on the items browse page

*********
Arguments
*********

:php:class:`Item` item
    The item object

:php:class:`Omeka_View` view
    The view object

********
Examples
********

.. code-block:: php

   public function hookAdminItemsBrowseDetailedEach($args)
   {
     $item = $args['item'];
     $embedTable = get_db()->getTable('Embed');
     $totalEmbeds = $embedTable->totalEmbeds($item->id);
     $html = '<p>';
     $html .= "<a href='" . url('embed-codes/item/' . $item->id) . "'>" . __('Embeds (%d)', $totalEmbeds) . "</a>";
     $html .= '</p>';
     echo $html;
   }
