Used to display secondary navigation elements within the browse and search pages.

The default value of the ``$navArray`` is:

.. code-block:: php

    $navArray = array(
            array(
                'label' =>__('Browse All'),
                'uri' => url('items/browse'),
            ));
            if (total_records('Tag')) {
                $navArray[] = array(
                    'label' => __('Browse by Tag'),
                    'uri' => url('items/tags')
                );
            }
            $navArray[] = array(
                'label' => __('Search Items'),
                'uri' => url('items/search')
            );

This displays the 'Browse All', 'Browse by Tag', and 'Search Items' navigation elements. Plugins such as Geolocation also add navigation elements to this array.

