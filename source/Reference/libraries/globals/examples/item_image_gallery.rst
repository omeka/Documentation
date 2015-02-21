Use the ``$attrs`` array to assign HTML attributes for each image in the gallery for an item. 

Use ``'wrapper'`` to set the attributes for gallery block ``div``:

.. code-block:: php

  <?php echo item_image_gallery(
    array('wrapper' => array('class' => 'gallery')));
  ?>

Use ``'linkWrapper'`` to set the attributes on the ``div`` that surrounds each image:

.. code-block:: php

  <?php echo item_image_gallery(
    array('wrapper' => array('class' => 'gallery'), 
    'linkWrapper' => array('class' => 'admin-thumb panel')));
  ?>
  
Use ``'link'`` to set the attributes for the ``a`` tag: 
 
.. code-block:: php

  <?php echo item_image_gallery(
    array('wrapper' => array('class' => 'gallery'), 
    'linkWrapper' => array('class' => 'admin-thumb panel'), 
    'link' => array('class' => 'link')));
  ?>
  
Use ``'image'`` to set the attribute for the ``img`` tag:

.. code-block:: php

  <?php echo item_image_gallery(
    array('wrapper' => array('class' => 'gallery'), 
    'linkWrapper' => array('class' => 'admin-thumb panel'), 
    'link' => array('class' => 'link'),
    'image' => array('class' => 'image')));
  ?>
  
Omit the default ``'wrapper'`` attributes by setting it to null:

.. code-block:: php

  <?php echo item_image_gallery(
    array('wrapper' => null,
    'linkWrapper' => array('class' => 'admin-thumb panel'), 
    'link' => array('class' => 'link'),
    'image' => array('class' => 'image')));
  ?>
    
Use the ``$imageType`` parameter to set which image derivative is used in the gallery. Available options are ``square_thumbnail``, ``thumbnail``,  ``fullsize``, and ``original``:

.. code-block:: php

  <?php echo item_image_gallery(
    array('wrapper' => null, 
    'linkWrapper' => array('class' => 'admin-thumb panel'), 
    'link' => array('class' => 'link'), 
    'image' => array('class' => 'image')),
    'thumbnail');
  ?>
  
Set the ``$filesShow`` boolean to true to link each image file to its file/show page:

.. code-block:: php

  <?php echo item_image_gallery(
    array('wrapper' => null, 
    'linkWrapper' => array('class' => 'admin-thumb panel'), 
    'link' => array('class' => 'link'), 
    'image' => array('class' => 'image')),
    'thumbnail', 
    true);
  ?>
  
